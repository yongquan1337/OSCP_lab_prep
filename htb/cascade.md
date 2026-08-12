└─$ ldapsearch -x -H ldap://$ip -b "DC=cascade,DC=local" "(objectClass=user)" sAMAccountName | grep 'sAMAccountName:' | cut -d ' ' -f 2
CascGuest
CASC-DC1$
arksvc
s.smith
r.thompson
util
j.wakefield
s.hickson
j.goodhand
a.turnbull
e.crowe
b.hanson
d.burman
BackupSvc
j.allen
i.croft

cascadepwd at the bottom. rly hard to spot.  clk0bjVldmE=
<img width="693" height="733" alt="image" src="https://github.com/user-attachments/assets/55223510-3ee5-43ae-afa9-6859bb78321a" />

decrypted to rY4n5eva


SMB email that said
TempAdmin (password is the same as the normal admin account password). 
found this vnc file in s.smith with hex password. which became     sT333ve2
<img width="819" height="471" alt="image" src="https://github.com/user-attachments/assets/2b1ec134-3214-4888-960e-e2d35ba04466" />  
<img width="1477" height="99" alt="image" src="https://github.com/user-attachments/assets/a90cc2dc-39f5-42c3-b50f-3bb820a363ab" />

wdigest?
<img width="896" height="254" alt="image" src="https://github.com/user-attachments/assets/92cf4e34-b542-492f-9995-71f7a0e170c3" />

smb audit folder i got audit.db. i used sqlite3 to dump  BQO5l5Kj9MdErXx6Q6AGOw==
<img width="1843" height="646" alt="image" src="https://github.com/user-attachments/assets/03481100-4b26-4da6-9729-4cec96448aab" />

putting the file into windows and run through dnspy cascaudit.exe shows the decrypt string is  c4scadek3y654321  
<img width="781" height="324" alt="image" src="https://github.com/user-attachments/assets/1df3364d-9d64-41c5-bb2f-c63e7c9a6af3" />
in casccrypto.dll we find the iv  1tdyjCbY1Ix49842
<img width="644" height="187" alt="image" src="https://github.com/user-attachments/assets/318eb0f5-a2bb-4e94-9ad9-0f2d1a1f5074" />  
Key: c4scadek3y654321
IV: 1tdyjCbY1Ix49842
Mode: CBC
Encoding: UTF-8

wow. use cyberchef. base64 + aes decrypt kinda cool  . password   w3lc0meFr31nd
<img width="1024" height="624" alt="image" src="https://github.com/user-attachments/assets/aea9c60a-04ed-40b7-965a-1aeede76d789" />

password for ArkSvc
<img width="1491" height="86" alt="image" src="https://github.com/user-attachments/assets/1d3bad9c-256f-43e5-95fa-91f722311a02" />

arksvc is in ad recycle group  
Get-ADObject -filter 'isDeleted -eq $true' -includeDeletedObjects -Properties *  
password for tempadmin is
cascadeLegacyPwd                : YmFDVDNyMWFOMDBkbGVz
baCT3r1aN00dles

previously said admin has same password as tempadmin so just winrm  
<img width="1234" height="294" alt="image" src="https://github.com/user-attachments/assets/7bb20752-2f9f-4efe-906c-4ce111faa161" />

