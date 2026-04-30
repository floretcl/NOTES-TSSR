## COMMANDES WINDOWS TSSR
### 1. LIGNE DE COMMANDE (CMD)
#### Réseau et Connectivité
- ipconfig /all : Configuration complète (MAC, DNS, DHCP).
- ipconfig /displaydns : Affiche les entrées DNS mises en cache.
- ipconfig /release : Réinitialise (libère) l'adresse IP actuelle.
- ipconfig /renew : Demande une nouvelle adresse IP au serveur DHCP.
- nslookup [Nom] : Test de résolution de nom DNS.
- tracert [IP/Nom] : Trace la route vers une destination.
- route print ou netstat -r : Affiche la table de routage.
- netstat -n : Affiche les connexions actives (adresses numériques).
- arp -a : Affiche la mémoire cache ARP (liaisons IP/MAC).
- netsh interface ip delete arpcache : Efface le cache ARP.
#### Système et GPO
- gpupdate /force : Force l'application immédiate des stratégies de groupe.
- gpresult /r : Affiche le résumé des GPO appliquées (RSOP).
- sfc /scannow : Analyse et répare l'intégrité des fichiers système.
- net user [user] /domain : Vérifie les informations d'un compte dans l'AD.
### 2. POWERSHELL : ESSENTIELS & SYSTÈME
#### Gestion de l'exécution et Scripts
- Get-ExecutionPolicy : Voir le niveau de sécurité des scripts.
- Set-ExecutionPolicy [Restricted | Unrestricted | AllSigned | RemoteSigned] : Modifier les droits d'exécution.
- Lancer un script : .\script.ps1 ou powershell -File "chemin/vers/script.ps1".
#### Aide et Découverte
- Get-Help [Commande] : Afficher l'aide complète.
- Get-Command *[Mot]* : Trouver une commande par mot-clé.
- Get-History : Voir l'historique des commandes saisies.
#### Processus et Services
- Get-Service : Lister les services.
- Start-Service -Name [Nom] / Stop-Service : Gérer les services.
- Get-Process : Lister les processus actifs.
- Stop-Process -ID [N] ou -Name [Nom] : Arrêter un processus.
#### Diagnostic et Rapports
- Start-Transcript : Enregistre toute la session console dans un fichier texte.
- Test-NetConnection -ComputerName [IP] -Port [N] : Vérifie l'ouverture d'un port (TNC).
- ConvertTo-HTML :
	- Exemple : Get-Process | Select-Object Name, Status | ConvertTo-HTML > C:\processes.html (Génère un rapport web des processus).
### 3. ADMINISTRATION ACTIVE DIRECTORY (Module RSAT)
#### Gestion des Utilisateurs
- Get-ADUser -Identity [Login] -Properties * : Détails complets d'un utilisateur.
- New-ADUser : Créer un utilisateur.
	- Ex : New-ADUser -Name "Jean" -SamAccountName jdupont -Path "OU=Users,DC=lab,DC=local" -Enabled $true
- Set-ADUser -Identity [Login] -Replace @{title="Technicien"} : Modifier un attribut.
- Unlock-ADAccount -Identity [Login] : Déverrouiller un compte bloqué.
- Set-ADAccountPassword -Identity [Login] -Reset : Réinitialiser le mot de passe.
#### Gestion des Groupes et OU
- Get-ADGroup -Filter 'Name -like "*Compta*"' : Trouver un groupe.
- Add-ADGroupMember -Identity "[Groupe]" -Members [Login] : Ajouter un membre.
- Get-ADGroupMember -Identity "[Groupe]" : Lister les membres d'un groupe.
- Get-ADOrganizationalUnit -Filter * : Lister toutes les Unités d'Organisation.
- Get-ADComputer -Filter * : Lister les ordinateurs du domaine.
### 4. LOGIQUE POWERSHELL : PIPES ET FILTRES
PowerShell traite des objets et non du texte simple. On utilise le symbole | pour passer l'objet à la commande suivante.
- Le Filtre ( Where-Object) :
	- Get-Service | Where-Object {$_.Status -eq "Stopped"} (Affiche les services arrêtés).
- La Sélection ( Select-Object) :
	- Get-ADUser -Filter * | Select-Object Name, SamAccountName (Affiche uniquement deux colonnes).
- Le Tri ( Sort-Object) :
	- Get-Process | Sort-Object CPU -Descending (Classe par consommation CPU).
### 5. OUTILS GPO & DIAGNOSTIC AVANCÉ
- gpresult /h report.html : Génère un rapport HTML détaillé des GPO (très visuel).
- rsop.msc : Console graphique du "Jeu de stratégie résultant".
