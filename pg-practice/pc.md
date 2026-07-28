22/tcp    open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.9 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 62:36:1a:5c:d3:e3:7b:e1:70:f8:a3:b3:1c:4c:24:38 (RSA)
|   256 ee:25:fc:23:66:05:c0:c1:ec:47:c6:bb:00:c7:4f:53 (ECDSA)
|_  256 83:5c:51:ac:32:e5:3a:21:7c:f6:c2:cd:93:68:58:d8 (ED25519)
8000/tcp  open  http    ttyd 1.7.3-a2312cb (libwebsockets 3.2.0)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: ttyd/1.7.3-a2312cb (libwebsockets/3.2.0)
|_http-title: ttyd - Terminal
65432/tcp open  http    Uvicorn
|_http-server-header: uvicorn
|_http-title: Site doesn't have a title (text/plain; charset=utf-8).
| http-methods: 
|_  Supported Methods: POST
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

8000 gives me a cmd in a browser
<img width="951" height="239" alt="image" src="https://github.com/user-attachments/assets/8d8928a5-0561-4894-beff-572df0e99965" />

searching for port 65432 exploit gave me a rpc.py code
https://github.com/ehtec/rpcpy-exploit/blob/main/rpcpy-exploit.py

i didnt rly understand the output but i js changed the code in the exploit to a rev shell
<img width="1220" height="119" alt="image" src="https://github.com/user-attachments/assets/49fc020d-c8da-49aa-9409-5840d4af7a7a" />
<img width="573" height="98" alt="image" src="https://github.com/user-attachments/assets/2213f041-15e4-4f3b-9987-cd82875e6c37" />
<img width="407" height="71" alt="image" src="https://github.com/user-attachments/assets/2c2a9a7a-5479-4fc6-95e7-67da4a161e40" />



