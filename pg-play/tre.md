?$ nmap $ip -sC -sV -p-
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-29 09:28 +0000
Nmap scan report for 192.168.68.84
Host is up (0.0062s latency).
Not shown: 65532 closed tcp ports (reset)
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 99:1a:ea:d7:d7:b3:48:80:9f:88:82:2a:14:eb:5f:0e (RSA)
|   256 f4:f6:9c:db:cf:d4:df:6a:91:0a:81:05:de:fa:8d:f8 (ECDSA)
|_  256 ed:b9:a9:d7:2d:00:f8:1b:d3:99:d6:02:e5:ad:17:9f (ED25519)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
|_http-title: Tre
|_http-server-header: Apache/2.4.38 (Debian)
8082/tcp open  http    nginx 1.14.2
|_http-server-header: nginx/1.14.2
|_http-title: Tre
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.26 seconds

dirbuster

/adminer.php
http://192.168.68.84/mantisbt/config/a.txt
# --- Database Configuration ---
$g_hostname      = 'localhost';
$g_db_username   = 'mantissuser';
$g_db_password   = 'password@123AS';
$g_database_name = 'mantis';
$g_db_type       = 'mysqli';

# --- Security ---
$g_crypto_master_salt = 'dsf34H@sds$242347832842309843294829304djfkdjsfkd';	#  Random string of at least 16 chars, unique to the installation

<img width="439" height="254" alt="image" src="https://github.com/user-attachments/assets/30da6816-8c12-488d-b628-dc5f4572bfb2" />

i tried to bruteforce password hash to no avail.

credentials:
administrator	XiBejMub
tre	Tr3@123456A!

ssh into tre
<img width="857" height="84" alt="image" src="https://github.com/user-attachments/assets/883e925f-d450-4285-8529-1fa94dd6c7a7" />


using linenum-ng

[+] htpasswd files:
htpasswd files found!
/etc/apache2/.htpasswd
admin:$apr1$klmM2diE$hD.osekk3Zh3yho7NZlV50



