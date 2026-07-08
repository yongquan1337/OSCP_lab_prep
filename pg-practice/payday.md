# Nmap 7.95 scan initiated Wed Jul  8 05:09:13 2026 as: /usr/lib/nmap/nmap --privileged -p- -Pn -v --min-rate 1000 --max-rtt-timeout 1000ms --max-retries 5 -oN nmap_ports.txt 192.168.164.39
Nmap scan report for 192.168.164.39
Host is up (0.042s latency).
Not shown: 65527 closed tcp ports (reset)
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
110/tcp open  pop3
139/tcp open  netbios-ssn
143/tcp open  imap
445/tcp open  microsoft-ds
993/tcp open  imaps
995/tcp open  pop3s

<img width="1919" height="521" alt="image" src="https://github.com/user-attachments/assets/a9b1ff2a-94c6-4bca-a212-8e6ffc01f89a" />

site uses cms CS Cart.

login to /admin using admin admin
<img width="1921" height="322" alt="image" src="https://github.com/user-attachments/assets/319c2ef1-0d24-4d1d-a3d0-b389280d2264" />

use exploit file upload to get rev shell
https://www.exploit-db.com/exploits/48891

login to patrick using patrick. he is able to use sudo on everything
<img width="1261" height="377" alt="image" src="https://github.com/user-attachments/assets/9d2192d8-a735-4cca-8736-ad61fdb8425c" />





