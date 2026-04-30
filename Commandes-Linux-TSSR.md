# COMMANDES LINUX TSSR
### Caractères spéciaux

; : séparation de commandes sur le même ligne
| : faire la commande de droite avec les résultats de la commande de gauche
|| : faire la commande de droite si la commande de gauche échoue
&& : faire la commande de droite si la commande de gauche réussie
#### Variables
Déclaration
nom_de_variable = valeur
Utilisation
$nom_de_variable
Attribuer une commande à une variable
nom_de_variable = $(commande)
#### Fonctions
Syntaxe
function nom-de-la-fonction {
suite-de-commandes
}
nom-de-la-fonction
#### Conditions
Si alors
if condition ; then
actions;
fi
Si alors sinon
if condition ; then
actions;
else
actions;
fi
Si alors sinon si alors sinon
if condition ; then
actions;
elif condition2 ; then
actions;
else
actions;
fi
Switch case
case « valeur » in
cas1) action1;;
cas2) action2;;
cas3) action3;;
esac
For
for chaque_élément in $liste ; do
Actions_à_faire ;
done
While
while test ; do
Actions_à_faire_1
Actions_à_faire_2 ;
done
Until (Inverse de while)
until test ; do
Actions_à_faire_1
Action_à_faire_2 ;
done
#### Commande de bases
Affichage de donnée
Echo
Demande d’entrée de donnée
Read
Obtenir le shell actuel :
echo $Shell
Changer de répertoire :
cd [emplacement]
Revenir au répertoire utilisateur :
cd ou cd ~
Revenir au répertoire parent :
cd ..
Revenir au répertoire précédent :
cd -
Stopper/Tuer un programme :
Kill [numéro de PID]
Ouvrir un fichier compressé :
Tar -xvf [archive.tar]
Compresser un fichier ou dossier :
Tar -czvf [fichier de sortie] [fichier d’entrée]
Afficher la liste des processus de l’utilisateur en cours :
Ps (u pour plus d’informations ax pour montrer tous les processus
Afficher la liste des dossiers et fichiers :
ls (-a pour les fichiers cachés -l sous forme de liste avec informations)
Créer un fichier :
touch [nom_fichier]
Supprimer un fichier :
Rm (-i pour une demande de confirmation -r effacement récursif)
Créer un répertoire :
Mkdir [nom_répertoire]
Défiler un fichier à l’écran :
More [fichier]
Rechercher une chaine de caractère dans un fichier :
Grep [chaîne] [fichier]
Rechercher un fichier ou dossier :
Find [nom]
#### Utilisateur et groupe
Afficher le nom d’utilisateur courant :
whoami
Afficher des informations sur l’utilisateur :
id
Passer en root :
su
Ajouter un user au sudo:
Adduser [nom_utilisateur] sudo (à faire en root après avoir installé sudo)
Changer l’utilisateur courant :
su [nom_utilisateur]
Création d’un nouvel utilisateur :
sudo useradd -m [nom_utilisateur]
Création d’un mot de passe utilisateur :
sudo passwd [nom_utilisateur]
Modifier le mot de passe de l’utilisateur courant :
passwd
Supprimer un utilisateur :
userdel [nom_utilisateur]
Création d’un nouveau groupe :
sudo groupadd [nom_du_groupe]
Ajout d’un utilisateur à un groupe :
sudo usermod -aG [nom_du_groupe] [nom_utilisateur]
Lister les utilisateurs d’un groupe :
getent group [nom_du_groupe]
Permissions
r : read
w : écriture
x : exécution
s : setuid (pour utilisateur) Pour autoriser d’autres utilisateurs que le propriétaire à exécuter
g : setgid (pour groupe) Pour attribuer au groupe tout nouveau fichier, répertoire
t: sticky bit (pour autres)
Modifier les permissions de fichier ou répertoire :
chmod [droits] [fichier]
Options de droits :
u : utilisateur
g : groupe
o : autres
- : ajouter
- : enlever
= : régler les droits exact
Exemples:
chmod u+rwx [fichier]
chmod 755 [fichier]
Modifier le propriétaire (utilisateur) :
chown [nom_utilisateur] [fichier]
Modifier le groupe :
chgrp [groupe] [fichier]
Définir les droits par défaut de fichier/répertoire crée par l’utilisateur courant :
umask [droits avec lettres ou sous forme d’octet à soustraire]
Exemple :
umask u-w (enlèvera l’écriture à l’utilisateur)
umask 200 (enlèvera l’écriture à l’utilisateur)
Résultat droits répertoire = 777 - 200 => 577
Résultat droits fichier = 666 - 200 => 466
Réseau
Informations sur le DHCP :
sudo nmap --script broadcast-dhcp-discover -e nom_interface
Configuration ip :
Ifconfig
Ip address (ou ip a)
networksetup -listallnetworkservices (sur macOS)
networksetup -getinfo Wi-Fi (sur macOS)
Cache arp :
arp
arp - a
Supprimer le cache arp
arp -d
Scripting
Utiliser l’extension sh
Déclarer un fichier en script bash
!/bin/bash
Ajouter les droits d’exécution seulement
Chmod +x [fichier.sh]
Commentaire
[commentaire]
Exécuter un script
Sh [script.sh]
./script.sh
Automatisation / CRON
Affiche la liste des actions planifiées
Crontab -l
Supprimer toutes les actions planifiées
Crontab -r
Ajouter/Modifier les actions planifiées
Crontab -e
Syntaxe
mm hh jj MMM JJJ tâche > log
- mm : minutes (00-59).
- hh : heures (00-23) .
- jj : jour du mois (01-31).
- MMM : mois (01-12 ou abréviation anglaise sur trois lettres : jan, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec).
- JJJ : jour de la semaine (1-7 ou abréviation anglaise sur trois lettres : mon, tue, wed, thu, fri, sat, sun).
- tâche : commande à exécuter.
- 
	> log (facultatif) : redirection de la sortie vers un fichier de log. Si un fichier de log n'est pas spécifié, un mail sera envoyé à l'utilisateur local.
Pour chaque unité, on peut utiliser les notations suivantes :
"*" : toutes les valeurs
	
- 
	- : plage de valeurs
- "," : séparateur de valeurs
- "/" :  Ignore des séquences de valeurs
Exemples
- 1-5 : les unités de temps de 1 à 5.
- */6 : toutes les 6 unités de temps (toutes les 6 heures par exemple).
- 2,7 : les unités de temps 2 et 7.
### 💻 Administration Windows (CMD & PowerShell)
#### Réseau & Diagnostic
- ipconfig /all : Détails complets des cartes (MAC, DHCP, DNS).
- ipconfig /release & /renew : Libérer et redemander un bail DHCP.
- nslookup <nom_domaine> : Tester la résolution DNS.
- tracert <ip_ou_nom> : Tracer la route jusqu'à une destination.
- netstat -an : Voir tous les ports ouverts et connexions actives.
- test-netconnection -computername <IP> -port <N>(PowerShell) : Vérifier si un port spécifique est ouvert à distance.
#### Système & Active Directory
- gpupdate /force : Forcer l'application des GPO immédiatement.
- gpresult /r : Afficher le résumé des GPO appliquées sur l'utilisateur/ordinateur.
- net user <username> /domain : Voir les infos d'un utilisateur dans l'AD.
- sfc /scannow : Réparer les fichiers système corrompus.
### 🐧 Administration Linux (Debian / Ubuntu / CentOS)
#### Gestion des droits & Utilisateurs
- chmod <octal> <fichier> : Modifier les permissions (ex: chmod 755 = rwxr-xr-x).
- chown <user>:<group> <fichier> : Modifier le propriétaire et le groupe.
- useradd -m <nom> : Créer un utilisateur avec son répertoire /home.
- passwd <nom> : Définir ou changer le mot de passe d'un utilisateur.
#### Sudo & Privilèges
- sudo <commande> : Exécuter une commande avec les droits root.
- sudo visudo : La seule méthode sûre pour modifier le fichier /etc/sudoers.
	- Ajout d'un user : Ajoute la ligne nom_user ALL=(ALL:ALL) ALL à la fin.
- usermod -aG sudo <nom_user> : Ajouter un utilisateur au groupe sudo (sur Debian/Ubuntu) pour lui donner les droits sans modifier le fichier manuellement.
#### Réseau & Services
- ip a : Afficher les adresses IP (remplace le vieux ifconfig).
- ip route : Afficher la table de routage (passerelle).
- systemctl <start|stop|restart|status|enable> <service> : Gérer les services (ex: apache2, ssh).
- tail -f /var/log/syslog : Lire les logs en temps réel pour débugger.
- ss -tunlp : Voir les ports en écoute (plus moderne que netstat).
## 🛡️ MÉMO COMMANDES TSSR : WINDOWS vs LINUX
### 🌐 1. Réseau et Diagnostic
			Action
			Commande Windows (CMD/PS)
			Commande Linux (Bash)
			Infos IP
			ipconfig /all
			ip a
			Passerelle / Route
			route print
			ip route
			Libérer IP (DHCP)
			ipconfig /release
			sudo dhclient -r
			Renouveler IP (DHCP)
			ipconfig /renew
			sudo dhclient
			Test DNS
			nslookup google.fr
			dig google.fr ou host google.fr
			Tracé de route
			tracert 8.8.8.8
			traceroute 8.8.8.8
			Ports en écoute
			netstat -an
			ss -tunlp (ou netstat -tulp)
			Test port précis
			tnc <IP> -p <Port> (PowerShell)
			nc -zv <IP> <Port> (Netcat)
### 🔑 2. Droits et Utilisateurs
#### 
- Modifier les droits : chmod <octal> <fichier> (ex: 755 pour rwxr-xr-x).
- Modifier le proprio : sudo chown <user>:<group> <fichier>.
- Créer un utilisateur : sudo useradd -m <nom_user>.
- Changer un mot de passe : sudo passwd <nom_user>.
- Gestion Sudo :
	- sudo visudo : Pour modifier le fichier /etc/sudoers (Ajouter : user ALL=(ALL:ALL) ALL).
	- sudo usermod -aG sudo <user> : Ajoute l'utilisateur au groupe des administrateurs.
### ⚙️ 3. Services et Logs
#### 
- État d'un service : systemctl status <service> (ex: apache2, ssh, isc-dhcp-server).
- Relancer un service : sudo systemctl restart <service>.
- Activer au démarrage : sudo systemctl enable <service>.
- Lire les logs en direct : tail -f /var/log/syslog (ou /var/log/auth.log pour les connexions).

### ⏰ 4. Planification de tâches (CRON / CRONTAB)
Le service Cron permet d'exécuter des commandes ou des scripts automatiquement à des moments précis.
#### Les commandes de base
- crontab -e : Modifier le fichier crontab (éditer les tâches). Conseil : Choisis nano si on te demande l'éditeur.
- crontab -l : Lister les tâches planifiées pour l'utilisateur actuel.
- crontab -r : Supprimer toutes les tâches de l'utilisateur.
- sudo crontab -u <user> -e : Modifier la crontab d'un autre utilisateur.
#### Syntaxe d'une ligne Crontab
Une ligne se compose de 5 étoiles suivies de la commande :
* * * * * /chemin/vers/ma_commande
			Unité
			Valeurs possibles
			Minute
			0 - 59
			Heure
			0 - 23
			Jour du mois
			1 - 31
			Mois
			1 - 12
			Jour de la semaine
			0 - 7 (0 et 7 sont le dimanche)
#### Exemples fréquents à l'examen
- Tous les jours à 03h30 :
	30 3 * * * /usr/bin/script_sauvegarde.sh
- Toutes les heures (à la minute 0) :
	0 * * * * /usr/bin/commande
- Tous les lundis à 8h00 :
	0 8 * * 1 /usr/bin/commande
- Toutes les 15 minutes :
	*/15 * * * * /usr/bin/commande

## 🛡️ MÉMO TECHNIQUE TSSR :  LINUX
### 🐧 1. SYSTÈME UNIX / LINUX
#### ⌨️ Commandes de Base
- echo $SHELL : Obtenir le shell actuel.
- whoami : Afficher le nom d'utilisateur courant.
- id : Afficher les informations détaillées de l'utilisateur (UID, GID).
- cd [emplacement] : Changer de répertoire ( ~ : home, .. : parent, - : précédent).
- ls -al : Lister les fichiers (même cachés) avec détails.
- touch [fichier] : Créer un fichier vide.
- mkdir [nom] : Créer un répertoire.
- rm -ri [cible] : Supprimer (récursif + confirmation).
- more [fichier] : Défiler le contenu d'un fichier.
- grep [chaîne] [fichier] : Rechercher un texte dans un fichier.
- find [nom] : Rechercher un fichier ou dossier.
- ps aux : Liste complète des processus.
- kill [PID] : Stopper un programme via son identifiant.
#### 📦 Compression (Tar)
- tar -cvzf out.tar.gz in/ : Compresser (c: create, z: gzip).
- tar -xvzf archive.tar.gz : Extraire (x: extract).
### 🔑 2. UTILISATEURS, GROUPES ET DROITS
#### Gestion des Comptes
- su [user] : Changer d'utilisateur ( su - pour passer en root).
- sudo useradd -m [user] : Créer un utilisateur avec son dossier home.
- sudo passwd [user] : Créer/modifier le mot de passe d'un utilisateur.
- sudo userdel [user] : Supprimer un utilisateur.
- sudo groupadd [groupe] : Créer un groupe.
- sudo usermod -aG [groupe] [user] : Ajouter un utilisateur à un groupe.
- getent group [groupe] : Lister les membres d'un groupe.
- sudo adduser [user] sudo : Donner les droits root (Debian/Ubuntu).
#### Permissions (Chmod / Chown)
- Structure : u (user), g (group), o (others) | r (4), w (2), x (1).
- chmod 755 [fichier] : (rwxr-xr-x).
- chmod u+x [fichier] : Ajouter l'exécution au propriétaire.
- chown [user] [fichier] : Changer le propriétaire.
- chgrp [groupe] [fichier] : Changer le groupe.
- Bits spéciaux :
	- s (setuid/gid) : Exécute avec les droits du proprio/groupe.
	- t (sticky bit) : Seul le propriétaire peut supprimer son fichier dans un dossier commun.
#### Umask (Droits par défaut)
- Soustraire la valeur de l'umask aux droits max (777 répertoire / 666 fichier).
- umask 022 : Dossier = 755, Fichier = 644.
### 🌐 3. RÉSEAU (INTEROPÉRABILITÉ)
			Action
			Windows
			Linux
			IP / Interface
			ipconfig /all
			ip a ou ifconfig
			DHCP (Renew)
			ipconfig /renew
			sudo dhclient
			Cache ARP
			arp -a
			arp -a
			Flush ARP
			arp -d *
			arp -d [IP]
			DNS
			nslookup
			dig ou host
			Route
			tracert
			traceroute
- Test DHCP (Linux) : sudo nmap --script broadcast-dhcp-discover -e [interface]
### 📜 4. SCRIPTING BASH (SH)
#### Caractères Spéciaux
- ; : Séparateur (exécute à la suite).
- | : Pipe (redirige le résultat vers la commande suivante).
- && : "ET" (exécute la suite seulement si la première réussit).
- || : "OU" (exécute la suite seulement si la première échoue).
#### Variables & Syntaxe
- Déclaration : nom=valeur (pas d'espace !).
- Commande dans variable : var=$(ls).
- Entrée/Sortie : read [var] / echo $[var].
- Shebang : Toujours commencer par #!/bin/bash.
#### Structures de Contrôle
- Condition if :
	Bash
	```if [ condition ]; then
   # actions
elif [ cond2 ]; then
   # actions
else
   # actions
fi

```
- Boucle for : for i in $liste; do ... done
- Boucle while : while [ test ]; do ... done
- Case (Switch) :
	Bash
	```case $val in
   1) action ;;
   *) action_par_defaut ;;
esac

```
### ⏰ 5. AUTOMATISATION (CRONTAB)
- crontab -e : Modifier | crontab -l : Lister | crontab -r : Supprimer.
- Syntaxe : mm hh jj MMM JJJ commande > log
			Unité
			Format
			Exemple
			*
			Tous les...
			* * * * * (Toutes les minutes)
			-
			Plage
			1-5 (Du 1er au 5 du mois)
			,
			Séparateur
			1,15 (Le 1er et le 15)
			*/n
			Séquence
			*/10 (Toutes les 10 minutes)
## COMMANDES SYSTÈME UNIX / LINUX - BASH
### SYSTÈME UNIX / LINUX & BASH
#### Commandes de Base
- echo $SHELL : Obtenir le shell actuel.
- whoami / id : Nom d'utilisateur courant / Détails (UID, GID).
- cd : Changer de répertoire ( ~ : home, .. : parent, - : précédent).
- ls -al : Lister tout (fichiers cachés + détails).
- touch / mkdir : Créer un fichier vide / un répertoire.
- rm -ri : Supprimer (récursif + confirmation).
- more / tail -f : Lire un fichier / Suivre les logs en temps réel.
- grep [chaîne] [fichier] : Rechercher un texte.
- find [nom] : Rechercher un fichier/dossier.
- ps aux / kill [PID] : Lister / Stopper les processus.
#### Compression (Tar)
- tar -cvzf out.tar.gz in/ : Compresser (c: create, z: gzip).
- tar -xvzf archive.tar.gz : Extraire (x: extract).
#### Gestion des Utilisateurs et Groupes
- su - : Passer en root.
- sudo useradd -m [user] : Créer utilisateur + home.
- sudo passwd [user] : Définir/Changer le mot de passe.
- sudo groupadd [groupe] / sudo usermod -aG [groupe] [user] : Gérer les groupes.
- getent group [groupe] : Lister les membres d'un groupe.
- sudo userdel [user] : Supprimer un utilisateur.
- sudo visudo : Seule méthode sûre pour modifier /etc/sudoers.
#### Permissions et Droits
- Octal : r=4, w=2, x=1 (7=rwx, 5=rx).
- chmod [droits] [fichier] : Modifier permissions (ex: 755 ou u+rwx).
- chown [user]:[group] [fichier] : Modifier propriétaire et groupe.
- Bits spéciaux :
	- s (setuid/gid) : Exécute avec droits propriétaire.
	- t (sticky bit) : Seul le propriétaire peut supprimer son fichier dans un dossier commun.
- Umask : Droits par défaut.
	- Calcul : 777 (rép) ou 666 (fichier) - Valeur Umask.
	- Ex: umask 022 -> Rép: 755 / Fich: 644.
### SCRIPTING BASH & AUTOMATISATION
#### Caractères Spéciaux & Logique
- ; : Séparateur de commandes.
- | : Pipe (Résultat A devient entrée de B).
- && : Exécute B si A réussit.
- || : Exécute B si A échoue.
#### Variables et Fonctions
- Déclaration : nom=valeur (pas d'espace).
- Commande : var=$(commande).
- Utilisation : $var.
- Fonction : function nom { commandes; }.
#### Structures de Contrôle
- Condition if :
	Bash
	```if [ condition ]; then
   # actions
elif [ cond2 ]; then
   # actions
else
   # actions
fi

```
- Boucles :
	- for i in $liste; do ... done
	- while [ test ]; do ... done
	- until [ test ]; do ... done (Inverse de while)
- Case : case $val in cas1) action;; esac.
#### Automatisation (CRONTAB)
- crontab -e : Modifier | -l : Lister | -r : Supprimer.
- Syntaxe : mm hh jj MMM JJJ tâche > log
	- */15 : Toutes les 15 min.
	- 1-5 : Plage de valeurs.
### RÉSEAU & INTEROPÉRABILITÉ

			Action
			Windows (CMD/PS)
			Infos IP
			ipconfig /all
			Passerelle
			route print
			Libérer DHCP
			ipconfig /release
			Renouveler DHCP
			ipconfig /renew
			DNS
			nslookup
			Route
			tracert
			Ports ouverts
			netstat -an
			Test port TCP
			tnc [IP] -p [Port] (PS)
			Action
			Linux (Bash)
			Infos IP
			ip a
			Passerelle
			ip route
			Libérer DHCP
			sudo dhclient -r
			Renouveler DHCP
			sudo dhclient
			DNS
			dig ou host
			Route
			traceroute
			Ports ouverts
			ss -tunlp
			Test port TCP
			nc -zv [IP] [Port]
- Cache ARP : arp -a (Windows/Linux) | arp -d (Suppression).
- Scan DHCP : sudo nmap --script broadcast-dhcp-discover -e [interface].
