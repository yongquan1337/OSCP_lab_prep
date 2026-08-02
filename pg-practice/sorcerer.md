22/tcp    open  ssh      OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 81:2a:42:24:b5:90:a1:ce:9b:ac:e7:4e:1d:6d:b4:c6 (RSA)
|   256 d0:73:2a:05:52:7f:89:09:37:76:e3:56:c8:ab:20:99 (ECDSA)
|_  256 3a:2d:de:33:b0:1e:f2:35:0f:8d:c8:d7:8f:f9:e0:0e (ED25519)
80/tcp    open  http     nginx
| http-methods: 
|_  Supported Methods: GET HEAD
|_http-title: Site doesn't have a title (text/html).
111/tcp   open  rpcbind  2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100003  3           2049/udp   nfs
|   100003  3,4         2049/tcp   nfs
|   100005  1,2,3      42329/tcp   mountd
|   100005  1,2,3      59704/udp   mountd
|   100021  1,3,4      33065/tcp   nlockmgr
|   100021  1,3,4      51595/udp   nlockmgr
|   100227  3           2049/tcp   nfs_acl
|_  100227  3           2049/udp   nfs_acl
2049/tcp  open  nfs      3-4 (RPC #100003)
7742/tcp  open  http     nginx
|_http-title: SORCERER
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
8080/tcp  open  http     Apache Tomcat 7.0.4
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-favicon: Apache Tomcat
|_http-title: Apache Tomcat/7.0.4
33065/tcp open  nlockmgr 1-4 (RPC #100021)
35835/tcp open  mountd   1-3 (RPC #100005)
42329/tcp open  mountd   1-3 (RPC #100005)
43307/tcp open  mountd   1-3 (RPC #100005)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

port 80. 404 page
<img width="691" height="231" alt="image" src="https://github.com/user-attachments/assets/a3c4aa9a-828f-4145-9b29-bbc166f483d1" />

port 7742. Control panel login
<img width="728" height="462" alt="image" src="https://github.com/user-attachments/assets/0984d222-a711-4ade-8d8e-a036d4a5cbcf" />
zipped files
<img width="815" height="219" alt="image" src="https://github.com/user-attachments/assets/6a070398-ce96-41a9-ac31-38f7ce38f4b5" />
max has ssh keys. cant ssh into any tho.
<img width="405" height="71" alt="image" src="https://github.com/user-attachments/assets/90b9f4f1-0748-4426-8187-1d49134e48c5" />
max might be a user for tomcat port 8080. manager-gui:VTUD2XxJjf5LPmu6
<img width="441" height="67" alt="image" src="https://github.com/user-attachments/assets/f07b76f5-a9cc-483b-9ef7-f51e022946af" />
<img width="658" height="56" alt="image" src="https://github.com/user-attachments/assets/4e7372d1-302b-41bf-bd46-4070829dd60c" />
authorized keys. disables portforwarding
<img width="1908" height="124" alt="image" src="https://github.com/user-attachments/assets/7abc7240-36a9-43a2-ab61-2ef90d18e89b" />
unable to scp 
<img width="861" height="75" alt="image" src="https://github.com/user-attachments/assets/9b5a9970-e585-450a-8f89-bdae54257b51" />
use the -O flag to send the file
access
<img width="387" height="61" alt="image" src="https://github.com/user-attachments/assets/c28aea12-f789-46b0-8d29-491133ede973" />

port 8080. Apache Tomcat/7.0.4
<img width="1296" height="435" alt="image" src="https://github.com/user-attachments/assets/6b8e6245-0be2-4358-acfc-6163dde34fd9" />

suid shows start stop daemon
<img width="598" height="267" alt="image" src="https://github.com/user-attachments/assets/e5ec02bf-df71-4fb1-b83f-c5d20c78d0ce" />
<img width="547" height="102" alt="image" src="https://github.com/user-attachments/assets/61008e4d-9146-4926-8136-14332cab8a74" />

