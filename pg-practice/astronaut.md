22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 98:4e:5d:e1:e6:97:29:6f:d9:e0:d4:82:a8:f6:4f:3f (RSA)
|   256 57:23:57:1f:fd:77:06:be:25:66:61:14:6d:ae:5e:98 (ECDSA)
|_  256 c7:9b:aa:d5:a6:33:35:91:34:1e:ef:cf:61:a8:30:1c (ED25519)
80/tcp open  http    Apache httpd 2.4.41
|_http-title: Index of /
| http-ls: Volume /
| SIZE  TIME              FILENAME
| -     2021-03-17 17:46  grav-admin/
|_
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-methods: 
|_  Supported Methods: OPTIONS HEAD GET POST
Service Info: Host: 127.0.0.1; OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 80 grav
<img width="1303" height="514" alt="image" src="https://github.com/user-attachments/assets/0f91fb55-42a5-41c9-abfe-4077949fd53d" />
robots.txt
User-agent: *
Disallow: /backup/
Disallow: /bin/
Disallow: /cache/
Disallow: /grav/
Disallow: /logs/
Disallow: /system/
Disallow: /vendor/
Disallow: /user/
Allow: /user/pages/
Allow: /user/themes/
Allow: /user/images/
Allow: /
Allow: *.css$
Allow: *.js$
Allow: /system/*.js$

use grav exploit
https://www.exploit-db.com/exploits/49973
edit the target and the base64 payload
<img width="1404" height="109" alt="image" src="https://github.com/user-attachments/assets/c9094328-92f0-43bf-b258-a467af74c344" />
<img width="1143" height="283" alt="image" src="https://github.com/user-attachments/assets/5afd0595-50e6-4957-a95d-0163d350c4c3" />

suid bit had php. edit sudoers
<img width="1032" height="84" alt="image" src="https://github.com/user-attachments/assets/7ffdd7bf-3a78-4a55-b159-00f1f20426e7" />
