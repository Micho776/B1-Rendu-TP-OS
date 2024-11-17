# TP3 : Process et identite

# I-Utilisateurs

## 1. Liste des users

### 🌞 Afficher la ligne du fichier qui concerne votre utilisateur

```powershell
micho776@TP-OS:~$ cat /etc/passwd | grep micho776
micho776:x:1000:1000:micho776,,,:/home/micho776:/bin/bash
```

### 🌞 Afficher la ligne du fichier qui concerne votre utilisateur ET celle de root en même temps

```powershell
micho776@TP-OS:~$ cat /etc/passwd | grep -e micho776 -e root
root:x:0:0:root:/root:/bin/bash
micho776:x:1000:1000:micho776,,,:/home/micho776:/bin/bash
```

### 🌞 Afficher la liste des groupes d'utilisateurs de la machine

```powershell
micho776@TP-OS:~$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:
tty:x:5:
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:micho776
floppy:x:25:micho776
tape:x:26:
sudo:x:27:
audio:x:29:micho776
dip:x:30:micho776
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
shadow:x:42:
utmp:x:43:
video:x:44:micho776
sasl:x:45:
plugdev:x:46:micho776
staff:x:50:
games:x:60:
users:x:100:micho776
nogroup:x:65534:
systemd-journal:x:999:
systemd-network:x:998:
crontab:x:101:
input:x:102:
sgx:x:103:
kvm:x:104:
render:x:105:
netdev:x:106:micho776
tss:x:107:
systemd-timesync:x:997:
messagebus:x:108:
_ssh:x:109:
ssl-cert:x:110:
avahi-autoipd:x:111:
bluetooth:x:112:micho776
avahi:x:113:
lpadmin:x:114:micho776
pipewire:x:115:
fwupd-refresh:x:116:
scanner:x:117:saned,micho776
saned:x:118:
geoclue:x:119:
polkitd:x:996:
rtkit:x:120:
colord:x:121:
Debian-gdm:x:122:
micho776:x:1000:
gnome-initial-setup:x:995:
marmotte:x:1001:
```

### 🌞 Afficher la ligne du fichier qui concerne votre utilisateur ET celle de root en même temps

```powershell
micho776@TP-OS:~$ cat /etc/passwd | cut -d":" -f1,6 | grep -e micho776 -e root
root:/root
micho776:/home/micho776
```

## 2. Hash des passwords

### 🌞 Afficher la ligne qui contient le hash du mot de passe de votre utilisateur

```powershell
micho776@TP-OS:~$ su - root
Password:
root@TP-OS:~ sudo cat /etc/shadow | grep micho776
micho776:$y$j9T$YPowR.TS6FtsNj62axlv20$ic98kSlwKVMX56CjI86sXBilXeFuYOzEwfQtTRG0Rl1:20033:0:99999:7:::
```

## 3. Sudo

### A. Intro

### 🌞 Faites en sorte que votre utilisateur puisse taper n'importe quelle commande sudo

```powershell
micho776@TP-OS:~$ sudo usermod -aG sudo micho776
micho776@TP-OS:~$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:
tty:x:5:
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:micho776
floppy:x:25:micho776
tape:x:26:
sudo:x:27:micho776
audio:x:29:micho776
dip:x:30:micho776
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
shadow:x:42:
utmp:x:43:
video:x:44:micho776
sasl:x:45:
plugdev:x:46:micho776
staff:x:50:
games:x:60:
users:x:100:micho776
nogroup:x:65534:
systemd-journal:x:999:
systemd-network:x:998:
crontab:x:101:
input:x:102:
sgx:x:103:
kvm:x:104:
render:x:105:
netdev:x:106:micho776
tss:x:107:
systemd-timesync:x:997:
messagebus:x:108:
_ssh:x:109:
ssl-cert:x:110:
avahi-autoipd:x:111:
bluetooth:x:112:micho776
avahi:x:113:
lpadmin:x:114:micho776
pipewire:x:115:
fwupd-refresh:x:116:
scanner:x:117:saned,micho776
saned:x:118:
geoclue:x:119:
polkitd:x:996:
rtkit:x:120:
colord:x:121:
Debian-gdm:x:122:
micho776:x:1000:
gnome-initial-setup:x:995:
marmotte:x:1001:
(arg: 6) cat /etc/group ^C
micho776@TP-OS:~$ cat /etc/group | grep micho776
cdrom:x:24:micho776
floppy:x:25:micho776
sudo:x:27:micho776
audio:x:29:micho776
dip:x:30:micho776
video:x:44:micho776
plugdev:x:46:micho776
users:x:100:micho776
netdev:x:106:micho776
bluetooth:x:112:micho776
lpadmin:x:114:micho776
scanner:x:117:saned,micho776
micho776:x:1000:
```

### B. Practice

### 🌞 Créer un groupe d'utilisateurs

```powershell
micho776@TP-OS:~$ sudo groupadd stronk_admins
```

### 🌞 Créer un utilisateur

```powershell
micho776@TP-OS:~$ sudo groupadd stronk_admins
micho776@TP-OS:~$ sudo useradd -m imbob
micho776@TP-OS:~$ sudo passwd imbob
New password:
Retype new password:
passwd: password updated successfully
```

### 🌞 Prouver que l'utilisateur imbob est créé

```powershell
micho776@TP-OS:~$ cat /etc/passwd | grep imbob
imbob:x:1002:1003::/home/imbob:/bin/sh
```

### 🌞 Prouver que l'utilisateur imbob a un password défini

```powershell
micho776@TP-OS:~$ sudo cat  /etc/shadow | grep imbob
imbob:$y$j9T$Lp0X0f0LonUIQ6/M0EEl9/$fqPNQODULhfDMt.OrUbiiCEmvDKVRHsLsghLf0lkT45:20040:0:99999:7:::
```

### 🌞 Prouver que l'utilisateur imbob appartient au groupe stronk_admins

```powershell
micho776@TP-OS:~$ sudo usermod -aG stronk_admins imbob
micho776@TP-OS:~$ cat /etc/group | grep stronk_admins
stronk_admins:x:1002:imbob
```

### 🌞 Créer un deuxième utilisateur

```powershell
micho776@TP-OS:~$ sudo useradd imnotbobsorry
micho776@TP-OS:~$ sudo passwd imnotbobsorry
New password:
Retype new password:
passwd: password updated successfully
```

### 🌞 Modifier la configuration de sudo pour que

```powershell
sudo visudo
%stronk_admins ALL=(ALL) NOPASSWD: /usr/bin/apt, /usr/bin/apt-get
```

### 🌞 Créer le dossier /home/goodguy (avec une commande)

```powershell
micho776@TP-OS:/home$ sudo mkdir goodguy
micho776@TP-OS:/home$ sudo usermod -d /home/goodguy imbob
micho776@TP-OS:/home$ cat /etc/passwd | grep imbob
imbob:x:1002:1003::/home/goodguy:/bin/sh
```

### 🌞 Créer le dossier /home/badguy

```powershell
micho776@TP-OS:/home$ sudo mkdir badguy
micho776@TP-OS:/home$ sudo usermod -d /home/badguy imnotbobsorry
micho776@TP-OS:/home$ cat /etc/passwd | grep imnotbobsorry
imnotbobsorry:x:1003:1004::/home/badguy:/bin/sh
```

### 🌞 Changer le répertoire personnel de imnotbobsorry

```powershell
micho776@TP-OS:/home$ ls -l | grep goodguy
drwxr-xr-x  2 root     root     4096 Nov 12 11:41 goodguy

micho776@TP-OS:/home$ sudo chown imbob:imbob goodguy -R
micho776@TP-OS:/home$ ls -l | grep goodguy
drwxr-xr-x  2 imbob    imbob    4096 Nov 12 11:41 goodguy

micho776@TP-OS:/home$ sudo chown imnotbobsorry:imnotbobsorry badguy/ -R
micho776@TP-OS:/home$ ls -l | grep badguy
drwxr-xr-x  2 imnotbobsorry imnotbobsorry 4096 Nov 12 11:46 badguy
```

### 🌞 Prouver que les permissions du dossier /home/gooduy sont incohérentes

```powershell
micho776@TP-OS ls -ld /home/goodguy
drwxr-xr-x 2 root root 4096 Nov 12 18:17 /home/goodguy

```

### 🌞 Modifier les permissions de /home/goodguy

```powershell
micho776@TP-OS sudo chown -R imbob:imbob /home/goodguy
```

### 🌞 Modifier les permissions de /home/badguy

```powershell
micho776@TP-OS sudo chown -R imnotbobsorry:imnotbobsorry /home/badguy
```

### 🌞 Connectez-vous sur l'utilisateur imbob

```powershell
micho776@TP-OS su - imbob
Password:
$ bash
imbob@tpose:~$ pwd
/home/goodguy
imbob@tpose:~$ sudo echo Pentakill
[sudo] password for imbob:
Pentakill

```

### 🌞 Connectez-vous sur l'utilisateur imnotbobsorry

```powershell
imbob@tpose:~$ su - imnotbobsorry
Password:
$ bash
imnotbobsorry@tpose:~$ pwd
/home/badguy
imnotbobsorry@tpose:~$ sudo echo meow
[sudo] password for imnotbobsorry:
Sorry, user imnotbobsorry is not allowed to execute '/usr/bin/echo meow' as root on tpose.nyan.
imnotbobsorry@tpose:~$ sudo apt update
[sudo] password for imnotbobsorry:
Get:1 http://security.debian.org/debian-security bookworm-security InRelease [48.0 kB]
Hit:2 http://deb.debian.org/debian bookworm InRelease
Get:3 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
Fetched 103 kB in 3s (32.9 kB/s)

```

# II-Processes

## 1. Jouer avec la commande ps

### 🌞 Affichez les processus bash

```powershell
micho@Deb:~$ ps -ef | grep bash
micho       1258    1252  0 19:49 pts/0    00:00:00 -bash
micho       1574    1258  0 20:29 pts/0    00:00:00 grep bash
```

### 🌞 Affichez tous les processus lancés par votre utilisateur

```powershell
micho@Deb:~$ ps -ef | grep micho
micho        846       1  0 19:46 ?        00:00:00 /lib/systemd/systemd --user
micho        847     846  0 19:46 ?        00:00:00 (sd-pam)
micho        863     846  0 19:46 ?        00:00:00 /usr/bin/pulseaudio --daemonize=no --log-target=journal
micho        864     846  0 19:46 ?        00:00:00 /usr/bin/gnome-keyring-daemon --foreground --components=pkcs11,secrets --control-directory=/run/user/1000/keyring
micho        871     846  0 19:46 ?        00:00:00 /usr/bin/dbus-daemon --session --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
micho        872     841  0 19:46 ?        00:00:00 xfce4-session
micho        924     872  0 19:46 ?        00:00:00 /usr/bin/ssh-agent x-session-manager
micho        934     846  0 19:46 ?        00:00:00 /usr/libexec/at-spi-bus-launcher
micho        940     934  0 19:46 ?        00:00:00 /usr/bin/dbus-daemon --config-file=/usr/share/defaults/at-spi2/accessibility.conf --nofork --print-address 11 --address=unix:path=/run/user/1000/at-spi/bus_0
micho        950     846  0 19:46 ?        00:00:00 /usr/libexec/at-spi2-registryd --use-gnome-session
micho        960     846  0 19:46 ?        00:00:00 /usr/bin/gpg-agent --supervised
micho        962     872  0 19:46 ?        00:00:00 xfwm4
micho        965     846  0 19:46 ?        00:00:00 /usr/libexec/gvfsd
micho        977     872  0 19:46 ?        00:00:00 xfsettingsd
micho        986     872  0 19:46 ?        00:00:00 xfce4-panel
micho        990     872  0 19:46 ?        00:00:00 Thunar --daemon
micho        995     872  0 19:46 ?        00:00:00 xfdesktop
micho        999     872  0 19:46 ?        00:00:00 nm-applet
micho       1001     872  0 19:46 ?        00:00:00 light-locker
micho       1003     872  0 19:46 ?        00:00:00 /usr/lib/policykit-1-gnome/polkit-gnome-authentication-agent-1
micho       1005     872  0 19:46 ?        00:00:00 /usr/bin/python3 /usr/share/system-config-printer/applet.py
micho       1006     872  0 19:46 ?        00:00:00 xiccd
micho       1007     872  0 19:46 ?        00:00:00 xfce4-power-manager
micho       1009     872  0 19:46 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/notifyd/xfce4-notifyd
micho       1013     986  0 19:46 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libsystray.so 6 16777228 systray Status Tray Plugin Provides status notifier items (application indicators) and legacy systray items
micho       1016     986  0 19:46 ?        00:00:01 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libpulseaudio-plugin.so 8 16777229 pulseaudio PulseAudio Plugin Adjust the audio volume of the PulseAudio sound system
micho       1017     846  0 19:46 ?        00:00:00 /usr/libexec/gvfs-udisks2-volume-monitor
micho       1020     986  0 19:46 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libxfce4powermanager.so 9 16777230 power-manager-plugin Power Manager Plugin Display the battery levels of your devices and control the brightness of your display
micho       1029     986  0 19:46 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libnotification-plugin.so 10 16777231 notification-plugin Notification Plugin Notification plugin for the Xfce panel
micho       1031     965  0 19:46 ?        00:00:00 /usr/libexec/gvfsd-trash --spawner :1.14 /org/gtk/gvfs/exec_spaw/0
micho       1037     846  0 19:46 ?        00:00:00 /usr/libexec/gvfsd-metadata
micho       1044     846  0 19:46 ?        00:00:00 /usr/libexec/dconf-service
micho       1093     986  0 19:46 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libactions.so 14 16777232 actions Action Buttons Log out, lock or other system actions
root        1243     681  0 19:49 ?        00:00:00 sshd: micho [priv]
micho       1252    1243  0 19:49 ?        00:00:00 sshd: micho@pts/0
micho       1258    1252  0 19:49 pts/0    00:00:00 -bash
micho       1568     846  0 20:26 ?        00:00:00 /usr/lib/x86_64-linux-gnu/xfce4/xfconf/xfconfd
micho       1582    1258 99 20:29 pts/0    00:00:00 ps -ef
micho       1583    1258  0 20:29 pts/0    00:00:00 grep micho
```

### 🌞 Affichez le top 5 des processus qui utilisent le plus de RAM

```powershell
micho@Deb:~$ ps aux --sort=-rss | head -n 6 | tail -n 5 | tr -s ' ' | cut -d ' ' -f 11,6
116048 /usr/sbin/lightdm-gtk-greeter
100388 /usr/lib/xorg/Xorg
95200 xfwm4
76668 /usr/lib/xorg/Xorg
62032 xfdesktop
```

### 🌞 Affichez le PID du processus du service SSH

```powershell
 ps -ef | grep sshd
root         681       1  0 19:46 ?        00:00:00 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
root        1243     681  0 19:49 ?        00:00:00 sshd: micho [priv]
micho       1252    1243  0 19:49 ?        00:00:00 sshd: micho@pts/0
micho       1622    1258  0 20:44 pts/0    00:00:00 grep sshd
```

### 🌞 Affichez le nom du processus avec l'identifiant le plus petit

```powershell
micho@Deb:~$  ps -ef --sort pid | head -2
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 19:46 ?        00:00:00 /sbin/init
```

## 2. Parent, enfant, et meurtre

### 🌞 Déterminer le PID de votre shell actuel

```powershell
micho@Deb:~$ ps -ef | grep bash
micho       1258    1252  0 19:49 pts/0    00:00:00 -bash
micho       1648    1258  0 20:51 pts/0    00:00:00 grep bash
```

### 🌞 Déterminer le nom de ce processus

```powershell
micho@Deb:~$ ps -p 1157
    PID TTY          TIME CMD
```

### 🌞 Lancer un processus sleep 9999 en tâche de fond

```powershell
micho@Deb:~$ ps -ef | grep sleep
micho       1652    1258  0 20:53 pts/0    00:00:00 grep sleep
```

### 🌞 Fermez votre session SSH

```powershell
micho@Deb:~$ exit
logout
Connection to 192.168.56.102 closed.
PS C:\Users\miche> ssh micho@192.168.56.102
micho@192.168.56.102's password:
Linux Deb 6.1.0-27-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.115-1 (2024-11-01) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Nov 17 19:49:20 2024 from 192.168.56.3
micho@Deb:~$
```

# III-Services

## 1.Analyser un service existant

### 🌞 S'assurer que le service ssh est démarré

```powershell
micho@Deb:~$ systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/lib/systemd/system/ssh.service; enabled; preset: enabled)
     Active: active (running) since Sun 2024-11-17 19:46:25 CET; 2h 20min ago
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 665 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 681 (sshd)
      Tasks: 1 (limit: 2282)
     Memory: 5.5M
        CPU: 394ms
     CGroup: /system.slice/ssh.service
             └─681 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

Warning: some journal files were not opened due to insufficient permissions.
```

### 🌞 Isolez la ligne qui indique le nom du programme lancé

```powershell
micho@Deb:~$ sudo systemctl status ssh | grep "Main PID"
   Main PID: 681 (sshd)

```

### 🌞 Déterminer le port sur lequel écoute le service SSH

```powershell
micho@Deb:~$ sudo ss -lntp | grep ssh
LISTEN 0      128          0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=611,fd=3))
LISTEN 0      128             [::]:22           [::]:*    users:(("sshd",pid=611,fd=4))
```

### 🌞 Consulter les logs du service SSH

```powershell
micho@Deb:~$ sudo journalctl -xe -u ssh
Nov 17 19:46:24 Deb systemd[1]: Starting ssh.service - OpenBSD Secure Shell server...
░░ Subject: A start job for unit ssh.service has begun execution
░░ Defined-By: systemd
░░ Support: https://www.debian.org/support
░░
░░ A start job for unit ssh.service has begun execution.
░░
░░ The job identifier is 136.
Nov 17 19:46:25 Deb sshd[681]: Server listening on 0.0.0.0 port 22.
Nov 17 19:46:25 Deb sshd[681]: Server listening on :: port 22.
Nov 17 19:46:25 Deb systemd[1]: Started ssh.service - OpenBSD Secure Shell server.
░░ Subject: A start job for unit ssh.service has finished successfully
░░ Defined-By: systemd
░░ Support: https://www.debian.org/support
░░
░░ A start job for unit ssh.service has finished successfully.
░░
░░ The job identifier is 136.
Nov 17 19:49:20 Deb sshd[1243]: Accepted password for micho from 192.168.56.3 port 513>
Nov 17 19:49:20 Deb sshd[1243]: pam_unix(sshd:session): session opened for user micho(>
Nov 17 19:49:20 Deb sshd[1243]: pam_env(sshd:session): deprecated reading of user envi>
Nov 17 22:05:35 Deb sshd[1838]: Accepted password for micho from 192.168.56.3 port 524>
Nov 17 22:05:35 Deb sshd[1838]: pam_unix(sshd:session): session opened for user micho(>
Nov 17 22:05:35 Deb sshd[1838]: pam_env(sshd:session): deprecated reading of user envi>
~
```

## 2.Modification du service

### A. Configuration du service SSH

### 🌞 Identifier le fichier de configuration du serveur SSH

```powershell
micho@Deb:~$ ls -l /etc/ssh | grep config
-rw-r--r-- 1 root root   1650 Jun 22 21:38 ssh_config
drwxr-xr-x 2 root root   4096 Jun 22 21:38 ssh_config.d
-rw-r--r-- 1 root root   3223 Jun 22 21:38 sshd_config
drwxr-xr-x 2 root root   4096 Jun 22 21:38 sshd_config.d
```

### 🌞 Modifier le fichier de conf

```powershell
micho@Deb:~$ echo $RANDOM
11319
crea@tpos:/etc/ssh$ cat sshd_config | grep Port
Port 11319
#GatewayPorts no
```

### 🌞 Redémarrer le service

```powershell
logout
Connection to 192.168.56.102 closed.
PS C:\Users\miche> ssh micho@192.168.56.102
micho@192.168.56.102's password:
Linux Deb 6.1.0-27-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.115-1 (2024-11-01) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Nov 17 22:05:35 2024 from 192.168.56.3
```

### 🌞 Effectuer une connexion SSH sur le nouveau port

```powershell
# Solution PowerShell ici
```

### B. Le service en lui-même

### 🌞 Trouver le fichier ssh.service

```powershell
micho@Deb:~$ sudo find / -name "ssh.service"
/usr/lib/systemd/system/ssh.service
```

### 🌞 Déterminer quel est le programme lancé

```powershell
micho@Deb:/usr/lib/systemd/system$ cat ssh.service | grep ExecStart=
ExecStart=/usr/sbin/sshd -D $SSHD_OPTS
```

## 4. Créez votre propre service

### 🌞 Déterminer le dossier qui contient la commande python3

```powershell
micho@Deb:~$ which python3
/usr/bin/python3
```

### 🌞 Créez un fichier /etc/systemd/system/meow_web.service

```powershell
micho@Deb:~$ nano /etc/systemd/system/meow_web.service
micho@Deb:~$ sudo !!

```

### 🌞 Indiquez à l'OS que vous avez modifié les services

```powershell
micho@Deb:~$ systemctl daemon-reload
```

### 🌞 Démarrez votre service

```powershell
micho@Deb:~$ systemctl start meow_web
==== AUTHENTICATING FOR org.freedesktop.systemd1.manage-units ====
Authentication is required to start 'meow_web.service'.
Authenticating as: Utsu otp akshan plat,,, (utsu)
Password:
==== AUTHENTICATION COMPLETE ====

```

### 🌞 Assurez-vous que le service meow_web est actif

```powershell
micho@Deb:~$ systemctl status meow_web
● meow_web.service - Super serveur web MEOW
     Loaded: loaded (/etc/systemd/system/meow_web.service; disabled; pr>
     Active: active (running) since Wed 2024-11-13 10:19:58 CET; 19s ago
   Main PID: 3590 (python3)
      Tasks: 1 (limit: 2284)
     Memory: 8.9M
        CPU: 133ms
     CGroup: /system.slice/meow_web.service
             └─3590 /usr/bin/python3 -m http.server 8888

```

### 🌞 Déterminer le PID du processus Python en cours d'exécution

```powershell
micho@Deb:~$ sudo ss -tlp | grep ':8888'
LISTEN 0      5            0.0.0.0:8888       0.0.0.0:*    users:(("python3",pid=3590,fd=3))

```

### 🌞 Prouvez que le programme écoute derrière le port 8888

```powershell
micho@Deb:~$ ps -eo pid,user,cmd | grep 'python3 -m http.server' | grep -v grep
   3590 root     /usr/bin/python3 -m http.server 8888

```

### 🌞 Faire en sote que le service se lance automatiquement au démarrage de la machine

```powershell
micho@Deb:~$ systemctl enable meow_web
==== AUTHENTICATING FOR org.freedesktop.systemd1.manage-unit-files ====
Authentication is required to manage system service or unit files.
Authenticating as: Utsu otp akshan plat,,, (utsu)
Password:
==== AUTHENTICATION COMPLETE ====
==== AUTHENTICATING FOR org.freedesktop.systemd1.reload-daemon ====
Authentication is required to reload the systemd state.
Authenticating as: Utsu otp akshan plat,,, (utsu)
Password:
==== AUTHENTICATION COMPLETE ====

```
