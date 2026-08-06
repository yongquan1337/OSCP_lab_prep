22/tcp open  ssh     OpenSSH 8.9p1 Ubuntu 3ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
|_  256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
80/tcp open  http    Apache httpd 2.4.52 ((Ubuntu))
|_http-server-header: Apache/2.4.52 (Ubuntu)
|_http-title: Client Area 
| http-git: 
|   192.168.208.27:80/.git/
|     Git repository found!
|     Repository description: Unnamed repository; edit this file 'description' to name the...
|_    Last commit message: Ready For launch 
| http-robots.txt: 8 disallowed entries 
| /boxbilling/bb-data/ /bb-data/ /bb-library/ 
|_/bb-locale/ /bb-modules/ /bb-uploads/ /bb-vendor/ /install/
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 80. add to /etc/hosts
<img width="1543" height="611" alt="image" src="https://github.com/user-attachments/assets/f38b2f02-8517-4b44-a48e-b520fbe6ae72" />

explore the .git with git_dumper
python3 ~/tools/git_dumper.py http://bullybox.local/.git gg
in bbconfig mysql creds
admin:Playing-Unstylish7-Provided

exploitdb version sucked. use github
https://github.com/0xk4b1r/CVE-2022-3552/blob/main/CVE-2022-3552.py
change the user and password. and modify code to change rev shell ip
<img width="1124" height="239" alt="image" src="https://github.com/user-attachments/assets/b385cdfd-3696-45c9-8ac3-9c93f1ea2145" />

