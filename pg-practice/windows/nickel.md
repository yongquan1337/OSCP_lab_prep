PORT      STATE SERVICE       VERSION
21/tcp    open  ftp           FileZilla ftpd 0.9.60 beta
| ftp-syst: 
|_  SYST: UNIX emulated by FileZilla
22/tcp    open  ssh           OpenSSH for_Windows_8.1 (protocol 2.0)
| ssh-hostkey: 
|   3072 86:84:fd:d5:43:27:05:cf:a7:f2:e9:e2:75:70:d5:f3 (RSA)
|   256 9c:93:cf:48:a9:4e:70:f4:60:de:e1:a9:c2:c0:b6:ff (ECDSA)
|_  256 00:4e:d7:3b:0f:9f:e3:74:4d:04:99:0b:b1:8b:de:a5 (ED25519)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds?
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| ssl-cert: Subject: commonName=nickel
| Issuer: commonName=nickel
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-07-30T06:52:17
| Not valid after:  2027-01-29T06:52:17
| MD5:   c874:8634:d343:24be:9d8b:c55c:744e:688e
|_SHA-1: 4139:4e89:999d:59b1:1b02:ca24:9fa2:3837:34b0:d82c
|_ssl-date: 2026-07-31T06:58:28+00:00; -1s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: NICKEL
|   NetBIOS_Domain_Name: NICKEL
|   NetBIOS_Computer_Name: NICKEL
|   DNS_Domain_Name: nickel
|   DNS_Computer_Name: nickel
|   Product_Version: 10.0.18362
|_  System_Time: 2026-07-31T06:57:23+00:00
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
8089/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
| http-methods: 
|_  Supported Methods: GET
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-favicon: Unknown favicon MD5: 9D1EAD73E678FA2F51A70A933B0BF017
|_http-title: Site doesn't have a title.
33333/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Site doesn't have a title.
|_http-favicon: Unknown favicon MD5: 76C5844B4ABE20F72AA23CBE15B2494E
| http-methods: 
|_  Supported Methods: GET POST
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2026-07-31T06:57:26
|_  start_date: N/A
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required



port 8089. when clicked on buttons bring me to new ip with port 33333 saying not found
<img width="787" height="381" alt="image" src="https://github.com/user-attachments/assets/47acaa15-8de7-4034-b8c2-410117458b27" />
<img width="900" height="134" alt="image" src="https://github.com/user-attachments/assets/7e90fcba-44b0-4686-a7d2-778c0cfab810" />

port 33333. invalid token so is it expecting something?
<img width="579" height="151" alt="image" src="https://github.com/user-attachments/assets/08b1d62b-3c5e-4da5-b402-f47066b6fd8d" />
<img width="866" height="413" alt="image" src="https://github.com/user-attachments/assets/4d94c236-988e-4eae-8543-3013ff29f7c3" />
running procs give me current processes
<img width="674" height="476" alt="image" src="https://github.com/user-attachments/assets/5ce439d8-d045-4638-b5e3-aaba03a01b93" />
user details for ssh. ariah:NowiseSloopTheory139
<img width="871" height="72" alt="image" src="https://github.com/user-attachments/assets/b39d789e-1c39-47d3-9049-96f5c2ea0e4d" />
<img width="532" height="84" alt="image" src="https://github.com/user-attachments/assets/25c1ee40-2ddb-4789-b5c2-efc2c145a436" />
<img width="649" height="422" alt="image" src="https://github.com/user-attachments/assets/2f6143c2-17b3-422e-9591-78439fda441f" />

ftp same details
<img width="766" height="452" alt="image" src="https://github.com/user-attachments/assets/01f1c07b-5ca8-4d09-acdf-e9afe701f44c" />
pdf2john and crack password of pdf ariah4168 
<img width="1760" height="375" alt="image" src="https://github.com/user-attachments/assets/b3217daf-5488-4044-82bc-1e35eef17c7c" />
<img width="720" height="406" alt="image" src="https://github.com/user-attachments/assets/7da62fd3-4b78-4c24-82f7-e99c56c3db4e" />

netstat -ano shows port 80 is on
<img width="653" height="344" alt="image" src="https://github.com/user-attachments/assets/cb0053ac-24ce-45df-99bd-688f15a99fc8" />

infratstructure shows Temporary Command endpoint: http://nickel/?
<img width="570" height="94" alt="image" src="https://github.com/user-attachments/assets/2d7f6601-12dc-4e5f-a7c9-0d78c2e6d39b" />

using nc and encoding the payload
<img width="1121" height="49" alt="image" src="https://github.com/user-attachments/assets/2e582ed2-4ed3-4846-a572-fc22fbef672b" />
<img width="1304" height="240" alt="image" src="https://github.com/user-attachments/assets/4ae8641e-121c-4c9b-96ce-2ddbaf952661" />



