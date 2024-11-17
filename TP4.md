# TP4 : Safé d partission

## 3. Vérification

🌞 Lister les périphériques de stockage branchés à la machine :

```bash
micho@Deb:~$ lsblk
NAME               MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda                  8:0    0   20G  0 disk
└─sda1               8:1    0   20G  0 part
  ├─pentakill-root 254:0    0  9.3G  0 lvm  /
  ├─pentakill-Swap 254:1    0  1.9G  0 lvm  [SWAP]
  ├─pentakill-home 254:2    0  1.9G  0 lvm  /home
  └─pentakill-var  254:3    0  2.8G  0 lvm  /var
sr0                 11:0    1 1024M  0 rom
```

🌞 Lister les partitions en cours d'utilisation :
| Point de montage | Taille | Système de fichiers |
| ---------------- | ------ | ------------------- |
| `/` | 10G | ext4 |
| Swap | 2G | swap |
| `/home` | 2G | ext4 |
| `/var` | 3G | ext4 |
| Espace libre | 3G | / |

## 4. Taille et inodes

🌞 Lister la quantité d'inodes disponibles sur chaque partition :

🌞 Déterminer la taille (avec du) et l'inode (avec ls) de chacun des fichiers suivants :

# II. Partitioning

## 1. d disk partou

🌞 Repérer le nom des nouveaux disques :

🌞 Ajouter ces deux disques comme des PV LVM :

🌞 Créer un VG nommé cat :

🌞 Créer un LV nommé meoooow :

🌞 Formater la partition (le LV) en autre chose que ext4 :

🌞 Créer le point de montage /mnt/meow :

🌞 Monter la partition meoooow sur le point de montage que vous avez créé :

🌞 Vérifier avec la commande adaptée que la partition est utilisable et qu'elle fait 3G :

## 2. Grow !

🌞 Il reste 2G sur le disque dur principal :

🌞 Prouvez en affichant la liste des partitions que la partition fait désormais 2G de plus :

🌞 Agrandir la partition meoooow pour qu'elle occupe tout l'espace libre de son VG :

🌞 Déterminer la taille de la nouvelle partition:

## 3. Montage automatique

🌞 Modifier le fichier /etc/fstab pour que la partition soit montée /mnt/meow automatiquement :

## 4. Bonus : options de montage

⭐ Déterminer quelles options de montage permettrait d'améliorer le niveau de sécurité des données contenues sur une partition. :
