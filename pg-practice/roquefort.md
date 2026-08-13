21/tcp   open  ftp     ProFTPD 1.3.5b
22/tcp   open  ssh     OpenSSH 7.4p1 Debian 10+deb9u7 (protocol 2.0)
| ssh-hostkey: 
|   2048 aa:77:6f:b1:ed:65:b5:ad:14:64:40:d2:24:d3:9c:0d (RSA)
|   256 a9:b4:4f:61:2e:2d:9d:4c:48:15:fe:70:8e:fa:af:b3 (ECDSA)
|_  256 92:56:eb:af:c9:34:af:ea:a1:cf:9f:e1:90:dd:2f:61 (ED25519)
2222/tcp open  ssh     Dropbear sshd 2016.74 (protocol 2.0)
3000/tcp open  http    Golang net/http server


port 3000 © Gitea Version: 1.7.5 
<img width="1867" height="838" alt="image" src="https://github.com/user-attachments/assets/cf8f4f43-8b15-43f4-b52e-796425c858a3" />

create account in gitea  
<img width="1348" height="402" alt="image" src="https://github.com/user-attachments/assets/8e0f0471-2b31-450d-ab60-834d1eafc93c" />

create bash payload rev shell. start python server on port 21
<img width="1256" height="234" alt="image" src="https://github.com/user-attachments/assets/f1caff14-8395-4311-bbe1-29d9ca176aa5" />

edit exploit
<img width="939" height="196" alt="image" src="https://github.com/user-attachments/assets/35f17f07-2ded-45c8-96a4-24c0652d6002" />  
<img width="675" height="75" alt="image" src="https://github.com/user-attachments/assets/1c6bc989-0fcd-4ff2-ac7b-b3dae87fcc28" />

[WRITABLE!] drwxrwsrwx 2 root staff 4096 Apr 24  2020 /usr/local/bin
crontab
*/5 *   * * *   root    cd / && run-parts --report /etc/cron.hourly

chloe@roquefort:/usr/local$ echo $PATH
/usr/lib/git-core:/usr/lib/git-core:/usr/lib/git-core:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

run-parts is in /bin which is the very last. but i can edit usr/local/bin which runs first  
i created script called run-parts which changes suid bit and also runs rev shell just incase. both worked
<img width="471" height="71" alt="image" src="https://github.com/user-attachments/assets/d8ecc345-e0e4-4c76-a371-5b2ab0914d1b" />  
 <img width="467" height="42" alt="image" src="https://github.com/user-attachments/assets/c86c1dcc-de11-4efb-8584-b08a569c264e" />  
 <img width="750" height="255" alt="image" src="https://github.com/user-attachments/assets/b855ac7d-c59d-4e4c-a29b-84e0540893d4" />

 


