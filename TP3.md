# TP3 : Process et identite

# I-Utilisateurs

## 1. Liste des users

### 🌞 Afficher la ligne du fichier qui concerne votre utilisateur

```powershell
# Code PowerShell ici
```

### 🌞 Afficher la ligne du fichier qui concerne votre utilisateur ET celle de root en même temps

```powershell
# Solution PowerShell ici
```

### 🌞 Afficher la liste des groupes d'utilisateurs de la machine

```powershell
# Code PowerShell ici
```

### Solution🌞 Afficher la ligne du fichier qui concerne votre utilisateur ET celle de root en même temps

```powershell
# Solution PowerShell ici
```

## 2. Hash des passwords

### 🌞 Afficher la ligne qui contient le hash du mot de passe de votre utilisateur

```powershell
# Code PowerShell ici
```

## 3. Sudo

### A. Intro

### 🌞 Faites en sorte que votre utilisateur puisse taper n'importe quelle commande sudo

```powershell
# Solution PowerShell ici
```

### B. Practice

### 🌞 Créer un groupe d'utilisateurs

```powershell
# Solution PowerShell ici
```

### 🌞 Créer un utilisateur

```powershell
# Solution PowerShell ici
```

### 🌞 Prouver que l'utilisateur imbob est créé

```powershell
# Solution PowerShell ici
```

### 🌞 Prouver que l'utilisateur imbob a un password défini

```powershell
# Solution PowerShell ici
```

### 🌞 Prouver que l'utilisateur imbob appartient au groupe stronk_admins

```powershell
# Solution PowerShell ici
```

### 🌞 Créer un deuxième utilisateur

```powershell
# Solution PowerShell ici
```

### 🌞 Modifier la configuration de sudo pour que

```powershell
# Solution PowerShell ici
```

### 🌞 Créer le dossier /home/goodguy (avec une commande)

```powershell
# Solution PowerShell ici
```

### 🌞 Créer le dossier /home/badguy

```powershell
# Solution PowerShell ici
```

### 🌞 Changer le répertoire personnel de imnotbobsorry

```powershell
# Solution PowerShell ici
```

### 🌞 Prouver que les permissions du dossier /home/gooduy sont incohérentes

```powershell
# Solution PowerShell ici
```

### 🌞 Modifier les permissions de /home/goodguy

```powershell
# Solution PowerShell ici
```

### 🌞 Modifier les permissions de /home/badguy

```powershell
# Solution PowerShell ici
```

### 🌞 Connectez-vous sur l'utilisateur imbob

```powershell
# Solution PowerShell ici
```

### 🌞 Connectez-vous sur l'utilisateur imnotbobsorry

```powershell
# Solution PowerShell ici
```

# II-Processes

## 1. Jouer avec la commande ps

### 🌞 Affichez les processus bash

```powershell
# Solution PowerShell ici
```

### 🌞 Affichez tous les processus lancés par votre utilisateur

```powershell
# Solution PowerShell ici
```

### 🌞 Affichez le top 5 des processus qui utilisent le plus de RAM

```powershell
# Solution PowerShell ici
```

### 🌞 Affichez le PID du processus du service SSH

```powershell
# Solution PowerShell ici
```

### 🌞 Affichez le nom du processus avec l'identifiant le plus petit

```powershell
# Solution PowerShell ici
```

## 2. Parent, enfant, et meurtre

### 🌞 Déterminer le PID de votre shell actuel

```powershell
# Solution PowerShell ici
```

### 🌞 Déterminer le nom de ce processus

```powershell
# Solution PowerShell ici
```

### 🌞 Lancer un processus sleep 9999 en tâche de fond

```powershell
# Solution PowerShell ici
```

### 🌞 Fermez votre session SSH

```powershell
# Solution PowerShell ici
```

# III-Services

## 1.Analyser un service existant

### 🌞 S'assurer que le service ssh est démarré

```powershell
# Solution PowerShell ici
```

### 🌞 Isolez la ligne qui indique le nom du programme lancé

```powershell
# Solution PowerShell ici
```

### 🌞 Déterminer le port sur lequel écoute le service SSH

```powershell
# Solution PowerShell ici
```

### 🌞 Consulter les logs du service SSH

```powershell
# Solution PowerShell ici
```

## 2.Modification du service

### A. Configuration du service SSH

### 🌞 Identifier le fichier de configuration du serveur SSH

```powershell
# Solution PowerShell ici
```

### 🌞 Modifier le fichier de conf

```powershell
# Solution PowerShell ici
```

### 🌞 Redémarrer le service

```powershell
# Solution PowerShell ici
```

### 🌞 Effectuer une connexion SSH sur le nouveau port

```powershell
# Solution PowerShell ici
```

### B. Le service en lui-même

### 🌞 Trouver le fichier ssh.service

```powershell
# Solution PowerShell ici
```

### 🌞 Déterminer quel est le programme lancé

```powershell
# Solution PowerShell ici
```

## 4. Créez votre propre service

### 🌞 Déterminer le dossier qui contient la commande python3

```powershell
# Solution PowerShell ici
```

### 🌞 Créez un fichier /etc/systemd/system/meow_web.service

```powershell
# Solution PowerShell ici
```

### 🌞 Indiquez à l'OS que vous avez modifié les services

```powershell
# Solution PowerShell ici
```

### 🌞 Démarrez votre service

```powershell
# Solution PowerShell ici
```

### 🌞 Assurez-vous que le service meow_web est actif

```powershell
# Solution PowerShell ici
```

### 🌞 Déterminer le PID du processus Python en cours d'exécution

```powershell
# Solution PowerShell ici
```

### 🌞 Prouvez que le programme écoute derrière le port 8888

```powershell
# Solution PowerShell ici
```

### 🌞 Faire en sote que le service se lance automatiquement au démarrage de la machine

```powershell
# Solution PowerShell ici
```
