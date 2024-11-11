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
