21/tcp   open  ftp         vsftpd 3.0.2
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:192.168.45.162
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 3
|      vsFTPd 3.0.2 - secure, fast, stable
|_End of status
22/tcp   open  ssh         OpenSSH 7.4 (protocol 2.0)
| ssh-hostkey: 
|   2048 a2:ec:75:8d:86:9b:a3:0b:d3:b6:2f:64:04:f9:fd:25 (RSA)
|   256 b6:d2:fd:bb:08:9a:35:02:7b:33:e3:72:5d:dc:64:82 (ECDSA)
|_  256 08:95:d6:60:52:17:3d:03:e4:7d:90:fd:b2:ed:44:86 (ED25519)
80/tcp   open  http        Apache httpd 2.4.6 ((CentOS) OpenSSL/1.0.2k-fips PHP/5.4.16)
| http-methods: 
|   Supported Methods: GET HEAD POST OPTIONS TRACE
|_  Potentially risky methods: TRACE
|_http-title: Apache HTTP Server Test Page powered by CentOS
|_http-server-header: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/5.4.16
111/tcp  open  rpcbind     2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|_  100000  3,4          111/udp6  rpcbind
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: SAMBA)
445/tcp  open  netbios-ssn Samba smbd 4.10.4 (workgroup: SAMBA)
3306/tcp open  mysql       MariaDB 10.3.23 or earlier (unauthorized)
8081/tcp open  http        Apache httpd 2.4.6 ((CentOS) OpenSSL/1.0.2k-fips PHP/5.4.16)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/5.4.16
|_http-title: 400 Bad Request
Service Info: Host: QUACKERJACK; OS: Unix

port 80 testing centos apache site
<img width="1674" height="813" alt="image" src="https://github.com/user-attachments/assets/5e7da8b6-4990-44a4-8cab-5c75e2dc22aa" />

port 8081 https. rconfig site. rConfig Version 3.9.4 
<img width="1390" height="556" alt="image" src="https://github.com/user-attachments/assets/a3238309-0994-4574-9b55-8d7246de3fe3" />

ok first of all searchsploit. u would think all of the 3.9.4 exploits atleast one of them would work.NO. the one thats suppposed to work is the 3.9  
but also NO. it has an error. why? because https. one of the request.get doesnt have verify=false. i had to add it manually.
<img width="1869" height="384" alt="image" src="https://github.com/user-attachments/assets/6afd8660-ef9f-4fe4-a0bc-0464620f59fa" />

https://www.exploit-db.com/exploits/48208
<img width="776" height="494" alt="image" src="https://github.com/user-attachments/assets/7ce9857a-1946-4383-806b-7cf169444d2d" />
admin:1:dc40b85276a1f4d7cb35f154236aa1b2
<img width="420" height="118" alt="image" src="https://github.com/user-attachments/assets/e142a263-e74f-47ec-9349-2a56ce1a0e94" />

admin:abgrtyu

https://www.exploit-db.com/exploits/48241
RCE. 443 didnt work. luckiliy 80 worked
<img width="1154" height="326" alt="image" src="https://github.com/user-attachments/assets/5289092d-e918-4eef-8bb5-09dd89b88293" />

suid has find
easy priv
<img width="762" height="515" alt="image" src="https://github.com/user-attachments/assets/c6586165-072c-446c-9de8-b6bbdec8b37b" />
