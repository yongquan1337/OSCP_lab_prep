22/tcp    open  ssh        OpenSSH 7.4p1 Debian 10+deb9u7 (protocol 2.0)
| ssh-hostkey: 
|   2048 09:80:39:ef:3f:61:a8:d9:e6:fb:04:94:23:c9:ef:a8 (RSA)
|   256 83:f8:6f:50:7a:62:05:aa:15:44:10:f5:4a:c2:f5:a6 (ECDSA)
|_  256 1e:2b:13:30:5c:f1:31:15:b4:e8:f3:d2:c4:e8:05:b5 (ED25519)
80/tcp    open  http       nginx 1.10.3
| http-methods: 
|_  Supported Methods: GET HEAD
|_http-server-header: nginx/1.10.3
|_http-title: Welcome to nginx!
6379/tcp  open  redis      Redis key-value store 5.0.9
8080/tcp  open  http-proxy
|_http-favicon: Unknown favicon MD5: 152FF7D5AE5BDB84B33D4DCA31EB7CD3
| http-robots.txt: 3 disallowed entries 
|_/admin/ /reset/ /compose
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.1 404 Not Found
|     X-DNS-Prefetch-Control: off
|     X-Frame-Options: SAMEORIGIN
|     X-Download-Options: noopen
|     X-Content-Type-Options: nosniff
|     X-XSS-Protection: 1; mode=block
|     Referrer-Policy: strict-origin-when-cross-origin
|     X-Powered-By: NodeBB
|     set-cookie: _csrf=g1bLrh5PPptg66dkxGSVUOLT; Path=/
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 11098
|     ETag: W/"2b5a-Vs4LI3Y6b3UkpjK2QCqqHXqU08k"
|     Vary: Accept-Encoding
|     Date: Sun, 09 Aug 2026 06:58:45 GMT
|     Connection: close
|     <!DOCTYPE html>
|     <html lang="en-GB" data-dir="ltr" style="direction: ltr;" >
|     <head>
|     <title>Not Found | NodeBB</title>
|     <meta name="viewport" content="width&#x3D;device-width, initial-scale&#x3D;1.0" />
|     <meta name="content-type" content="text/html; charset=UTF-8" />
|     <meta name="apple-mobile-web-app-capable" content="yes" />
|     <meta name="mobile-web-app-capable" content="yes" />
|     <meta property="og:site_n
|   GetRequest: 
|     HTTP/1.1 200 OK
|     X-DNS-Prefetch-Control: off
|     X-Frame-Options: SAMEORIGIN
|     X-Download-Options: noopen
|     X-Content-Type-Options: nosniff
|     X-XSS-Protection: 1; mode=block
|     Referrer-Policy: strict-origin-when-cross-origin
|     X-Powered-By: NodeBB
|     set-cookie: _csrf=1RCdrslWfX1Zvel--hFlvXmH; Path=/
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 18181
|     ETag: W/"4705-OjBAZwaBRXGHhsFDFCfJUnX1dcA"
|     Vary: Accept-Encoding
|     Date: Sun, 09 Aug 2026 06:58:44 GMT
|     Connection: close
|     <!DOCTYPE html>
|     <html lang="en-GB" data-dir="ltr" style="direction: ltr;" >
|     <head>
|     <title>Home | NodeBB</title>
|     <meta name="viewport" content="width&#x3D;device-width, initial-scale&#x3D;1.0" />
|     <meta name="content-type" content="text/html; charset=UTF-8" />
|     <meta name="apple-mobile-web-app-capable" content="yes" />
|     <meta name="mobile-web-app-capable" content="yes" />
|     <meta property="og:site_name" content
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     X-DNS-Prefetch-Control: off
|     X-Frame-Options: SAMEORIGIN
|     X-Download-Options: noopen
|     X-Content-Type-Options: nosniff
|     X-XSS-Protection: 1; mode=block
|     Referrer-Policy: strict-origin-when-cross-origin
|     X-Powered-By: NodeBB
|     Allow: GET,HEAD
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 8
|     ETag: W/"8-ZRAf8oNBS3Bjb/SU2GYZCmbtmXg"
|     Vary: Accept-Encoding
|     Date: Sun, 09 Aug 2026 06:58:45 GMT
|     Connection: close
|     GET,HEAD
|   RTSPRequest: 
|     HTTP/1.1 400 Bad Request
|_    Connection: close
|_http-title: Home | NodeBB
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
27017/tcp open  mongodb    MongoDB 4.0.18 4.1.1 - 5.0
| mongodb-databases: 
|   errmsg = command listDatabases requires authentication
|   codeName = Unauthorized
|   ok = 0.0
|_  code = 13
| mongodb-info: 
|   MongoDB Build info
|     debug = false
|     gitVersion = 6883bdfb8b8cff32176b1fd176df04da9165fd67
|     modules
|     versionArray
|       2 = 18
|       3 = 0
|       0 = 4
|       1 = 0
|     sysInfo = deprecated

port 80 nginx server
<img width="1043" height="429" alt="image" src="https://github.com/user-attachments/assets/aef2be14-9f64-4909-9fc9-879ffcf1667b" />


port 8080. nodeBB
<img width="1477" height="594" alt="image" src="https://github.com/user-attachments/assets/94fce75b-9bb6-438c-902d-040073273404" />  

REDIS
<img width="1722" height="441" alt="image" src="https://github.com/user-attachments/assets/ca033a8d-1d01-41ca-abc4-09bf85ade47f" />

reverse shell for good measure
<img width="997" height="121" alt="image" src="https://github.com/user-attachments/assets/3ae0cc3c-6276-44a3-8c23-5ff075e5c258" />
<img width="1117" height="308" alt="image" src="https://github.com/user-attachments/assets/c60f69d0-336a-4ffd-b419-c60b1cd14cd9" />
