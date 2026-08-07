22/tcp    open  ssh           Bitvise WinSSHD 8.48 (FlowSsh 8.48; protocol 2.0; non-commercial use)
| ssh-hostkey: 
|   3072 21:25:f0:53:b4:99:0f:34:de:2d:ca:bc:5d:fe:20:ce (RSA)
|_  384 e7:96:f3:6a:d8:92:07:5a:bf:37:06:86:0a:31:73:19 (ECDSA)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds?
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
8080/tcp  open  http-proxy
|_http-generator: Actual Drawing 6.0 (http://www.pysoft.com) [PYSOFTWARE]
|_http-title: Argus Surveillance DVR
| fingerprint-strings: 
|   GetRequest, HTTPOptions: 
|     HTTP/1.1 200 OK
|     Connection: Keep-Alive
|     Keep-Alive: timeout=15, max=4
|     Content-Type: text/html
|     Content-Length: 985
|     <HTML>
|     <HEAD>
|     <TITLE>
|     Argus Surveillance DVR
|     </TITLE>
|     <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
|     <meta name="GENERATOR" content="Actual Drawing 6.0 (http://www.pysoft.com) [PYSOFTWARE]">
|     <frameset frameborder="no" border="0" rows="75,*,88">
|     <frame name="Top" frameborder="0" scrolling="auto" noresize src="CamerasTopFrame.html" marginwidth="0" marginheight="0"> 
|     <frame name="ActiveXFrame" frameborder="0" scrolling="auto" noresize src="ActiveXIFrame.html" marginwidth="0" marginheight="0">
|     <frame name="CamerasTable" frameborder="0" scrolling="auto" noresize src="CamerasBottomFrame.html" marginwidth="0" marginheight="0"> 
|     <noframes>
|     <p>This page uses frames, but your browser doesn't support them.</p>
|_    </noframes>
|_http-trane-info: Problem with XML parsing of /evox/about
| http-methods: 
|_  Supported Methods: GET HEAD
|_http-favicon: Unknown favicon MD5: 283B772C1C2427B56FC3296B0AF42F7C
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC

port 8080. argus surveilance
<img width="879" height="280" alt="image" src="https://github.com/user-attachments/assets/ced7f21f-5497-4e39-a6c1-bbbab7ca03c6" />
argus privesc
<img width="677" height="198" alt="image" src="https://github.com/user-attachments/assets/88bf0a08-75e8-47d8-8ee8-1f9ce82d07e2" />
argus directory traversal. shows system.ini file
<img width="1879" height="148" alt="image" src="https://github.com/user-attachments/assets/5eb5adc5-334b-4e9d-8e4a-6427acf4ceb1" />

in /users. theres administrator and viewer.
trying to get .ssh/id_rsa
<img width="1461" height="252" alt="image" src="https://github.com/user-attachments/assets/d48e48c8-88e8-4638-8047-90797efdbc81" />
able to get viewer id_rsa
<img width="1903" height="540" alt="image" src="https://github.com/user-attachments/assets/b260498d-f816-412b-b204-cae07d94c26f" />
chmod 600 id_rsa
sh -i id_rsa viewer@$ip
<img width="569" height="187" alt="image" src="https://github.com/user-attachments/assets/de27da41-5390-460a-8505-19f8728367ed" />

argus weak password 
https://github.com/s3l33/CVE-2022-25012/blob/main/README.md
i got the password for administrator
ImWatchingY0u
<img width="1014" height="567" alt="image" src="https://github.com/user-attachments/assets/46ac3295-f6fd-474e-ac9e-1ecd0e26ade2" />

i also got 14WatchD0g$
run as only worked with 14WatchD0g$
<img width="1134" height="235" alt="image" src="https://github.com/user-attachments/assets/82871a8f-34dd-48be-ba9e-f0b92965ca4e" />


