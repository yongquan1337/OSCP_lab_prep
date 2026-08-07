1978/tcp open  remotemouse    Emote Remote Mouse
1979/tcp open  unisql-java?
1980/tcp open  pearldoc-xact?
3389/tcp open  ms-wbt-server  Microsoft Terminal Services
|_ssl-date: 2026-08-07T13:49:08+00:00; 0s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: REMOTE-PC
|   NetBIOS_Domain_Name: REMOTE-PC
|   NetBIOS_Computer_Name: REMOTE-PC
|   DNS_Domain_Name: Remote-PC
|   DNS_Computer_Name: Remote-PC
|   Product_Version: 10.0.19041
|_  System_Time: 2026-08-07T13:48:40+00:00
| ssl-cert: Subject: commonName=Remote-PC
| Issuer: commonName=Remote-PC
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-07-15T23:24:15
| Not valid after:  2027-01-14T23:24:15
| MD5:   be96:ffa6:263a:c279:7cd2:7a18:aac4:edcf
|_SHA-1: 149f:2aa3:314b:390f:1bc9:d4d9:ca2e:342f:25b1:339a
7680/tcp open  pando-pub?
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

remotemouse exploit
<img width="859" height="145" alt="image" src="https://github.com/user-attachments/assets/1511525b-f45c-49fd-94f5-c95b1db3758a" />
<img width="1347" height="248" alt="image" src="https://github.com/user-attachments/assets/9bcca250-d6bf-4914-9372-21489d0945f1" />

using find str pass
<img width="514" height="95" alt="image" src="https://github.com/user-attachments/assets/66dc01fa-33ec-4d0f-9df3-8672c7e69789" />
in recent servers found base 64 password. gives ControlFreak11
<img width="636" height="293" alt="image" src="https://github.com/user-attachments/assets/2b839a45-f880-4db3-8a64-dbacfee11bd7" />

use remote mouse priv esc
https://www.exploit-db.com/exploits/50047
