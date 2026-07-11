PORT     STATE SERVICE
22/tcp   open  ssh
23/tcp   open  telnet
80/tcp   open  http
3306/tcp open  mysql

after using ferox, i found the /test 
<img width="1224" height="356" alt="image" src="https://github.com/user-attachments/assets/fa92bb0f-9676-4836-a072-6cca63aebe56" />

inspecting, it says version 1.4.1.4
<img width="466" height="50" alt="image" src="https://github.com/user-attachments/assets/7805c6be-23e7-4ab4-a7a8-3f6cca941499" />

using the 1.4.1.4 version, i run the php exploit.
<img width="1879" height="617" alt="image" src="https://github.com/user-attachments/assets/3c4cc726-defa-42de-95c5-8c4ee3b9a608" />

run revshell
<img width="643" height="68" alt="image" src="https://github.com/user-attachments/assets/0d0f1b85-324e-4701-90bb-ca51c3a67eca" />
<img width="1152" height="348" alt="image" src="https://github.com/user-attachments/assets/3c88e101-c78e-490d-9a13-84a8a3d670a8" />

in zp-data folder theres a config file. root:hola
<img width="739" height="38" alt="image" src="https://github.com/user-attachments/assets/462e9181-14c1-4131-87d3-f537704b531c" />

found hash in zenphoto db 63e5c2e178e611b692b526f8b6332317f2ff5513 
<img width="866" height="447" alt="image" src="https://github.com/user-attachments/assets/f24d8905-2698-494c-9067-e5ba47ff8d82" />

found another hash in mysql database
<img width="1914" height="395" alt="image" src="https://github.com/user-attachments/assets/d3459d45-efec-4139-83f4-43db9153b174" />

both hashes ended up being loop holes.

i ran linux exploit suggester. dirty cow didnt work.
<img width="1573" height="684" alt="image" src="https://github.com/user-attachments/assets/1f14b122-67e8-4b71-a013-429ab199ae79" />

rds worked
<img width="587" height="416" alt="image" src="https://github.com/user-attachments/assets/dff70b15-5097-45f0-93a2-c7055d425a83" />

pwnkit also worked
<img width="455" height="173" alt="image" src="https://github.com/user-attachments/assets/4f38cf47-08ba-43cf-a30b-9b303d4bc1f2" />
