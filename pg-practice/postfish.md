22/tcp  open  ssh
25/tcp  open  smtp
80/tcp  open  http
110/tcp open  pop3
143/tcp open  imap
993/tcp open  imaps
995/tcp open  pop3s



add postfish.off into /etc/hosts
<img width="572" height="117" alt="image" src="https://github.com/user-attachments/assets/8322253c-5fca-4e2b-99db-3467106c27a4" />

website
<img width="1413" height="578" alt="image" src="https://github.com/user-attachments/assets/27ade3a9-d363-4f77-96e9-6cc273910b01" />

used usernames from the website into a usernamer.py to get possible users
<img width="741" height="154" alt="image" src="https://github.com/user-attachments/assets/6077e519-be47-4923-b931-28b79d2f58a4" />

using smtp-user-enum to find valid smtp users
<img width="736" height="476" alt="image" src="https://github.com/user-attachments/assets/8dc75d21-3454-4901-bd8d-a23db254a040" />
<img width="971" height="553" alt="image" src="https://github.com/user-attachments/assets/2469e901-35b0-4743-b65c-96d8e39d9135" />
<img width="534" height="410" alt="image" src="https://github.com/user-attachments/assets/07f3b6e2-0d69-4a4c-933e-dcca5becf230" />

hydra -L valid_users.txt -e nsr $ip pop3 -V -f 
always use -e nsr first, lowest hanging fruit
sales:sales for pop
<img width="770" height="74" alt="image" src="https://github.com/user-attachments/assets/c4222d08-4ec3-4cff-aee5-a31b5a7956cb" />

login to sales
<img width="1275" height="574" alt="image" src="https://github.com/user-attachments/assets/cdfda21c-7175-4a1d-94b6-f83444bb6bf4" />

sales team will be resetting password and brian is in sales
<img width="1914" height="555" alt="image" src="https://github.com/user-attachments/assets/6667ad96-eef8-4bd3-8c35-b15b4c27d5fd" />

send phishing email. phishing kinda not tested in oscp though but wtv
<img width="513" height="346" alt="image" src="https://github.com/user-attachments/assets/1ab08aba-4739-44b5-b6e9-cbb94a8c7476" />
<img width="1791" height="209" alt="image" src="https://github.com/user-attachments/assets/cc0eeb8a-5236-484f-aa37-9367b864476a" />
brian.moore:EternaLSunshinE  

writeable files
/etc/postfix/disclaimer
<img width="465" height="40" alt="image" src="https://github.com/user-attachments/assets/a1c71991-28cb-438a-9c45-d1a9864ea046" />

add rev shell into disclaimer and then send email from it to brian
<img width="385" height="287" alt="image" src="https://github.com/user-attachments/assets/d02a30e4-c289-4de7-9d58-94ab6963989f" />
<img width="1106" height="344" alt="image" src="https://github.com/user-attachments/assets/e29b69d1-3a02-48c5-a6fd-b700a6e2bcfa" />

shell into filter user and sudo -l shows mail
<img width="1049" height="100" alt="image" src="https://github.com/user-attachments/assets/49830dd8-3243-44fc-8d28-1b88495848af" />
<img width="543" height="67" alt="image" src="https://github.com/user-attachments/assets/a1299acf-1c65-436a-828d-e174dece0048" />
