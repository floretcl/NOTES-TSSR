# Commande CISCO IOS Routeur et Switch

## COMMANDES CISCO IOS 
### 1. MODES ET ACCÈS GÉNÉRAUX
- enable : Accès mode privilégié (Prompt #).
- configure terminal (ou conf t) : Mode configuration globale.
- exit : Retour au niveau précédent.
- end (ou Ctrl+Z) : Retour direct au mode privilégié.
- no [X]  : Désactive une configuration.
- copy running-config startup-config (ou wr) : Sauvegarder en NVRAM.
### 2. CONFIGURATION DE BASE & SÉCURITÉ
#### Système et Identification
- hostname [NOM] : Nommer l'équipement.
- banner motd #[MESSAGE]# : Message d'avertissement légal.
- no ip domain-lookup : Désactive la recherche DNS (évite les blocage sur erreurs de frappe).
- service password-encryption : Chiffre les mots de passe dans la config.
#### Sécurisation des accès
- enable secret [MDP] : Mot de passe du mode privilégié (chiffré).
- security passwords min-length [N] : Longueur minimale des mots de passe.
- username [NOM] secret [MDP] : Créer un utilisateur local.
- login block-for [DUREE BLOCAGE SEC] attempts [NB ESSAIS] within [DUREE ESSAIS SEC] : Protection contre les attaques brute-force.
#### Lignes (Console et Distante)
- line console [0] : Configuration du port physique.
- line vty [0 4] : Configuration Telnet/SSH.
- password [MDP] puis login : Authentification simple.
- login local : Utilise les comptes username locaux.
- transport input [ssh | telnet | all | none] : Choix du protocole.
- exec-timeout [MIN] [SEC] : Temps d'inactivité avant déconnexion.

### 3. CONFIGURATION IP & INTERFACES
#### IPv4 & IPv6
- interface [TYPE/NUMERO] : Entrer dans la config du port (ex: int g0/0).
- interface range [DEBUT]-[FIN] : Configurer un groupe de ports (ex: int range f0/1-24).
- description [TEXTE] : Label de l'interface.
- ip address [IP] [MASQUE] : Assigner une IPv4.
- ipv6 address [IP/PREFIX] [LINK-LOCAL] : Assigner une IPv6 global ou local
- ipv6 unicast-routing : Requis sur routeur pour acheminer l'IPv6.
- no shutdown : Activer l'interface.
- duplex [auto | full | half] : Mode de transmission.
#### Spécifique Switch (Commutateur)
- vlan [ID]name [NOM] : Créer un VLAN.
- switchport mode access puisswitchport access vlan [ID] : Assigner un port à un VLAN.
- switchport mode trunk : Faire passer plusieurs VLAN sur un port (802.1Q).
- interface vlan 1 puisip address [IP] [MASQUE] : IP de management du Switch.
- ip default-gateway [IP PASSERELLE] : Passerelle par défaut du Switch.
### 4. ROUTAGE ET SERVICES
- ip route [IP_DEST] [MASQUE] [IP_PASSERELLE] : Route statique IPv4.
- no ip http server : Désactiver l'interface web (sécurité).
- no ip directed-broadcasts : Désactiver les diffusions dirigées (autorise 255.255.255.255 seulement).
- auto secure : Assistant de sécurisation global.
#### Pré-requis SSH
1. ip domain-name [NOM DE DOMAINE] : Défini un nom de domaine
2. crypto key generate rsa general-keys modulus [1024/2048] : Définin une clé de chiffrement SSH
3. line vty  puis login local puis transport input ssh.
### 5. VÉRIFICATION ET DIAGNOSTIC (SHOW)
#### États et Performances
- show [ip/ipv6] interface brief : État résumé des ports (UP/DOWN) et IPs.
- show [ip/ipv6] interfaces : État des ports (UP/DOWN) et IPs.
- show [ip/ipv6] interface [] : État d'un port (UP/DOWN) et IP.
- show interface [] : État de toutes les interfaces.
- show ip ports all : Liste des ports ouverts (anciennement : show control-panel host open-ports).
- show running-config : Configuration actuelle en RAM.
- show ip route : Table de routage.
- show arp : Cache ARP (correspondances IP/MAC).
- show vlan brief : (Switch uniquement) Liste des VLANs et ports.
- show protocols : Protocoles actifs.
- show version : Infos matériel, logiciel et registre.
#### Voisinage (CDP)
- show cdp neighbors [detail] : Voir les voisins (même sans ping réussi) (Cisco).
- no cdp run : Désactiver CDP globalement.
- no cdp enable : Désactiver CDP sur une interface seule.
#### Debugging
- debug [NOM_PROTOCOLE] : Surveillance temps réel (ex: debug ip icmp). 
- undebug all (ou no debug all) : Arrêter tous les debugs.
- terminal monitor : Affiche les logs/debugs sur une session distante (SSH/Telnet).
- terminal no monitor : Désactive l'affichage des logs/debugs.

## CONFIGURATION COMPLÈTE : ROUTEUR CISCO
#### 1. Sécurisation et Accès
Cisco CLI
```enable
configure terminal
hostname R1
no ip domain-lookup                 ! Évite les blocages sur erreurs de frappe
enable secret class                 ! Mot de passe mode privilégié (chiffré)
service password-encryption         ! Chiffrer tous les mots de passe visibles
banner motd #ACCES PRIVE - R1#      ! Message d'avertissement

```
#### 2. Configuration SSH
Cisco CLI
```ip domain-name lab.local            ! Requis pour générer les clés
crypto key generate rsa             ! Choisir 2048 bits
username admin secret cisco         ! Utilisateur local pour SSH
line vty 0 4                        ! Accès à distance
 transport input ssh                ! Désactive Telnet (insécure)
 login local                        ! Utilise la base de données locale
 exec-timeout 5 0                   ! Déconnexion auto après 5 min
exit

```
#### 3. Interfaces et Routage (IPv4/IPv6)
Cisco CLI
```ipv6 unicast-routing                ! Activer le routage IPv6 globalement
interface GigabitEthernet0/0/0
 description LIEN_LAN
 ip address 192.168.1.254 255.255.255.0
 ipv6 address fe80::1 link-local
 ipv6 address 2001:db8:acad:1::1/64
 no shutdown                        ! ACTIVER LE PORT
exit

! Route par défaut vers le fournisseur d'accès (Internet)
ip route 0.0.0.0 0.0.0.0 [IP_SUIVANT]

```
## CONFIGURATION COMPLÈTE : SWITCH CISCO

#### 1. Sécurité de base
Cisco CLI
```enable
configure terminal
hostname SW1
enable secret class
line console 0
 logging synchronous                ! Empêche les logs de couper votre saisie
exit

```
#### 2. Gestion des VLANs
Cisco CLI
```vlan 10
 name COMPTA
vlan 20
 name INFORMATIQUE
exit

```
#### 3. Assignation des Ports
Cisco CLI
```! Ports d'accès (Ordinateurs, Imprimantes)
interface range fastEthernet 0/1-10
 switchport mode access
 switchport access vlan 10
 no shutdown

! Port Trunk (Lien vers Routeur ou autre Switch)
interface fastEthernet 0/24
 switchport mode trunk
 description TRUNK_VERS_R1

```
#### 4. Adresse de Management (SVI)
Cisco CLI
```! Permet de prendre la main sur le switch à distance via son IP
interface vlan 1
 ip address 192.168.1.10 255.255.255.0
 no shutdown
exit
ip default-gateway 192.168.1.254    ! Passerelle pour joindre le switch hors du LAN

```
