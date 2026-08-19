80/tcp   open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-favicon: Unknown favicon MD5: 6DC825C260AFEEA86DFCFEE3B99F13BF
|_http-title: Slick - Bootstrap 4 Template
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-methods: 
|_  Supported Methods: HEAD GET POST OPTIONS
3306/tcp open  mysql   MariaDB 5.5.5-10.3.34
| mysql-info: 
|   Protocol: 10
|   Version: 5.5.5-10.3.34-MariaDB-0ubuntu0.20.04.1
|   Thread ID: 16
|   Capabilities flags: 63486
|   Some Capabilities: Support41Auth, InteractiveClient, LongColumnFlag, Speaks41ProtocolNew, SupportsLoadDataLocal, ODBCClient, SupportsTransactions, ConnectWithDatabase, IgnoreSigpipes, IgnoreSpaceBeforeParenthesis, Speaks41ProtocolOld, DontAllowDatabaseTableColumn, FoundRows, SupportsCompression, SupportsMultipleResults, SupportsAuthPlugins, SupportsMultipleStatments
|   Status: Autocommit
|   Salt: *YcgZo>&C],`$,R:gxH=
|_  Auth Plugin Name: mysql_native_password


port 80 slick
<img width="1359" height="781" alt="image" src="https://github.com/user-attachments/assets/186707d4-2d71-43ad-9c4f-861a405ef937" />

/bugtracker  
<img width="1298" height="667" alt="image" src="https://github.com/user-attachments/assets/82711ae5-ec2a-4c01-9376-e877b3f39819" />

/bugtracker/install.php arbitrary file read  
<img width="1916" height="514" alt="image" src="https://github.com/user-attachments/assets/404b8930-5403-4e82-b73d-6820ef21959b" />
<img width="900" height="697" alt="image" src="https://github.com/user-attachments/assets/969e0508-a118-4645-b131-e2e930861062" />

try to read config file  /bugtracker/config/config_inc.php
<img width="881" height="341" alt="image" src="https://github.com/user-attachments/assets/bfb23ee4-60e8-46e0-8f67-63154270eba0" />  

got it with trial and error with the /var  
<img width="1046" height="264" alt="image" src="https://github.com/user-attachments/assets/b58afce9-7c39-4e3a-8b77-a0aa6a69b9e4" />
$g_hostname               = 'localhost';
$g_db_type                = 'mysqli';
$g_database_name          = 'bugtracker';
$g_db_username            = 'root';
$g_db_password            = 'SuperSequelPassword';

$g_default_timezone       = 'UTC';

$g_crypto_master_salt     = 'OYAxsrYFCI+xsFw3FNKSoBDoJX4OG5aLrp7rVmOCFjU=';

login to mysql  
<img width="770" height="398" alt="image" src="https://github.com/user-attachments/assets/5796c74a-29ab-400c-a30d-8170e14500d4" />

crack the administrator password to  
prayingmantis

login  mantis 2.5.2
<img width="978" height="260" alt="image" src="https://github.com/user-attachments/assets/61391dda-8234-41f8-9ac7-5d0718f9287f" />

https://mantisbt.org/bugs/view.php?id=26091  
get reverse shell from this
<img width="1313" height="219" alt="image" src="https://github.com/user-attachments/assets/de0d4f14-6195-4e21-a5e5-adb5b898fb28" />  
pspy64
<img width="831" height="64" alt="image" src="https://github.com/user-attachments/assets/9385385a-6a62-4a33-801a-1c91b4b23155" />

bugtracker : BugTracker007  
<img width="481" height="63" alt="image" src="https://github.com/user-attachments/assets/831dbf93-51f0-4e95-896f-f3ee1c7c4643" />

