# TP2

## 1-Gameshell

## 2-Files and Users

### I-Fichiers

#### A-Find Me

1/

```powershell
cat /etc/passwd
/home/micho776
```

2/

```powershell
micho776@TP-OS:~$ ls -l
total 40
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Desktop
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Documents
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Downloads
drwxr-xr-x 3 micho776 micho776 4096 Nov 11 20:01 gameshell
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Music
-rw------- 1 micho776 micho776    3 Nov 11 16:54 nano.2788.save
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Pictures
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Public
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Templates
drwxr-xr-x 2 micho776 micho776 4096 Nov  6 11:49 Videos
```

3/

```powershell
micho776@TP-OS:~$ cd /etc/ssh/
micho776@TP-OS:/etc/ssh$ ls
moduli        sshd_config.d           ssh_host_ed25519_key.pub
ssh_config    ssh_host_ecdsa_key      ssh_host_rsa_key
ssh_config.d  ssh_host_ecdsa_key.pub  ssh_host_rsa_key.pub
sshd_config   ssh_host_ed25519_key
```

### II-Users

#### A-Nouveau User

1/

```powershell
useradd -m -d /home/papier_alu marmotte
passwd marmotte
```

#### B- Infos Enregistres par le Systeme

1/

```powershell
root@TP-OS:~ cat /etc/passwd | grep marmotte
marmotte:x:1001:1001::/home/papier_alu:/bin/sh
```

2/

```powershell
root@TP-OS:~ sudo cat /etc/shadow | grep marmotte
marmotte:$y$j9T$xUBV.Wsoih8Mxrh9njY8y.$ArkteL1G9PuWBoZ6xNQj6Aszf5huXXAXh1mQcNXhhv2:20038:0:99999:7:::
```

#### D-Connexion sur le Nouvel Utilisateur

1/

```powershell
micho776@TP-OS:~$ exit
logout
Connection to 192.168.25.37 closed.
PS C:\Users\miche> ssh marmotte@192.168.25.37
marmotte@192.168.25.37's password:
Linux TP-OS 6.1.0-26-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.112-1 (2024-09-30) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
ls
ls: cannot open directory '/home/micho776': Permission denied
```

## 3-Programmes et Paquets

### I-Programmes et Processus

#### A- Run then Kill

1/

```powershell
sleep 1000
ps -A | grep sleep
 9674 pts/1    00:00:00 sleep
```

2/

```powershell
kill  9674
```

#### B-Tache de Fond

1/

```powershell
sleep 1000&
```

2/

```powershell
ps -e | grep sleep
  9683 pts/1    00:00:00 sleep
```

#### C-Find Paths

1/

```powershell
find / -type f -name ".bashrc"
/usr/bin/sleep
/usr/lib/klibc/bin/sleep
```

2/

```powershell
find / -type f -name ".bashrc"
/home/micho776/gameshell/gameshell/World/.bashrc
/home/micho776/.bashrc
/home/papier_alu/.bashrc
/etc/skel/.bashrc
```

#### D-La Variable Path

1/

```powershell
micho776@TP-OS:~$ which sleep
/usr/bin/sleep
micho776@TP-OS:~$ which ssh
/usr/bin/ssh
micho776@TP-OS:~$ which ping
/usr/bin/ping
micho776@TP-OS:~$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
```

### II-Paquets

1/

```powershell
micho776@TP-OS:~$ su - root
Password:
root@TP-OS:~ sudo apt install git
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
```

2/

```powershell
micho776@TP-OS:~$ which firefox
/usr/bin/firefox
```

3/

```powershell
micho776@TP-OS:~$ cat /etc/apt/sources.list
#deb cdrom:[Debian GNU/Linux 12.7.0 _Bookworm_ - Official amd64 NETINST with firmware 20240831-10:38]/ bookworm contrib main non-free-firmware

deb http://deb.debian.org/debian/ bookworm main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware

deb http://security.debian.org/debian-security bookworm-security main non-free-firmware
deb-src http://security.debian.org/debian-security bookworm-security main non-free-firmware

# bookworm-updates, to get updates before a point release is made;
# see https://www.debian.org/doc/manuals/debian-reference/ch02.en.html#_updates_and_backports
deb http://deb.debian.org/debian/ bookworm-updates main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm-updates main non-free-firmware

# This system was installed using small removable media
# (e.g. netinst, live or single CD). The matching "deb cdrom"
# entries were disabled at the end of the installation process.
# For information about how to configure apt package sources,
# see the sources.list(5) manual.
```

## 4-Poupee Russe

1/

```powershell
micho776@TP-OS:~$ wget https://gitlab.com/it4lik/b1-os/-/raw/main/tp/2/meow
--2024-11-12 01:22:13--  https://gitlab.com/it4lik/b1-os/-/raw/main/tp/2/meow
Resolving gitlab.com (gitlab.com)... 172.65.251.78, 2606:4700:90:0:f22e:fbec:5bed:a9b9
Connecting to gitlab.com (gitlab.com)|172.65.251.78|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18016947 (17M) [application/octet-stream]
Saving to: ‘meow’

meow                  100%[========================>]  17.18M  13.5MB/s    in 1.3s

2024-11-12 01:22:15 (13.5 MB/s) - ‘meow’ saved [18016947/18016947]
```

2/

```powershell
micho776@TP-OS:~/Downloads$ file meow
meow: Zip archive data, at least v2.0 to extract, compression method=deflate
micho776@TP-OS:~/Downloads$ mv meow meow.zip
micho776@TP-OS:~/Downloads$ ls
meow.zip
```

3/

```powershell
micho776@TP-OS:~/Downloads$ unzip meow.zip
Archive:  meow.zip
  inflating: meow
micho776@TP-OS:~/Downloads$ ls
meow  meow.zip
micho776@TP-OS:~/Downloads$ file meow
meow: XZ compressed data, checksum CRC64
micho776@TP-OS:~/Downloads$ mv meow meow.xz
micho776@TP-OS:~/Downloads$ xz -d meow.xz
micho776@TP-OS:~/Downloads$ file meow
meow: bzip2 compressed data, block size = 900k
micho776@TP-OS:~/Downloads$ bzip2 -d meow
bzip2: Can't guess original name for meow -- using meow.out
file meow.out
meow.out: RAR archive data, v5
micho776@TP-OS:~/Downloads$ sudo apt install unrar-free
micho776@TP-OS:~/Downloads$ unrar meow.out

unrar-free 0.1.3  Copyright (C) 2004  Ben Asselstine, Jeroen Dekkers


Extracting from /home/micho776/Downloads/meow.out

Extracting  meow                                                      OK
All OK
micho776@TP-OS:~/Downloads$ file meow
meow: gzip compressed data, from Unix, original size modulo 2^32 145049600 gzip compressed data, reserved method, has CRC, extra field, has comment, from FAT filesystem (MS-DOS, OS/2, NT), original size modulo 2^32 145049600
micho776@TP-OS:~/Downloads$ mv meow.gzip meow.gz
micho776@TP-OS:~/Downloads$ gzip -d meow.gz
micho776@TP-OS:~/Downloads$ file meow
meow: POSIX tar archive (GNU)
micho776@TP-OS:~/Downloads$ mv meow meow.tar
micho776@TP-OS:~/Downloads$ tar -xvf meow.tar
```

4/

```powershell
micho776@TP-OS:~/Downloads/dawa$ find . -type f -size 15M
./folder31/19/file39
micho776@TP-OS:~/Downloads/dawa$  grep -L '[^7]' * -r
folder43/38/file41
micho776@TP-OS:~/Downloads/dawa$ find . -type f -name "cookie"
./folder14/25/cookie
micho776@TP-OS:~/Downloads/dawa$ find . -type f -name ".*"
./folder32/14/.hidden_file
micho776@TP-OS:~/Downloads/dawa$ find . -type f -newermt "2014-01-01" ! -newermt "2015-01-01"
./folder36/40/file43
micho776@TP-OS:~/Downloads/dawa$ find . -type f -path './*/*/*/*/*/*'
./folder37/45/23/43/54/file43

```
