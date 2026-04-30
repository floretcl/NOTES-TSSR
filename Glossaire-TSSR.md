## Glossaire TSSR

### Général

#### Architecture et Réseaux de Communication
- Interconnexion des réseaux : Action de relier plusieurs réseaux informatiques (locaux ou distants) afin de permettre l'échange de données entre des hôtes situés sur des segments différents.
- SDN (Software-defined networking) : Architecture réseau qui sépare le plan de contrôle (intelligence logicielle) du plan de données (matériel de transfert). Cela permet une gestion centralisée et programmable du réseau.
- POP (FAI) - Point de présence : Infrastructure technique située à un endroit géographique précis où le fournisseur d'accès (FAI) installe ses équipements pour permettre aux clients locaux de se connecter à son réseau.
- WLL (Wireless Local Loop) : Boucle locale sans fil. Technologie permettant de relier un abonné au réseau de l'opérateur via des ondes radio plutôt que par un câble physique.
- IXP (Internet Exchange Point) : Infrastructure physique permettant à différents acteurs (FAI, hébergeurs) d'échanger du trafic Internet directement entre leurs réseaux.
- NAP (Network Access Point) : Ancêtre de l'IXP, il s'agissait des points d'interconnexion majeurs du trafic Internet lors de sa création.
- WISP (Wireless Internet Service Provider) : Fournisseur d'accès qui propose une connexion Internet via des technologies sans fil (Wi-Fi, ondes radio), souvent utilisé dans les zones rurales.
- Portail captif : Interface web imposée à l'utilisateur lors de sa première connexion à un réseau (souvent Wi-Fi public) pour authentification, paiement ou acceptation des conditions d'utilisation.
#### Équipements et Protocoles Réseaux
- Équipements actifs du réseau : Matériels qui traitent et régulent le trafic de données (Switches, Routeurs, Firewalls, Bornes Wi-Fi), par opposition aux équipements passifs (câbles, baies, prises).
- Meraki, Ubiquiti, Aruba, HP : Constructeurs d'équipements réseau. Meraki (Cisco) est connu pour son management via le Cloud ; Ubiquiti (UniFi) pour son rapport qualité/prix et son contrôleur logiciel ; Aruba (HPE) pour ses solutions Wi-Fi d'entreprise.
- Cisco IOS : Système d'exploitation propriétaire utilisé sur la majorité des routeurs et commutateurs Cisco.
- SVI (Switch Virtual Interface) : Interface logique (Layer 3) configurée sur un switch pour permettre le routage entre VLANs ou l'administration à distance du switch via une adresse IP.
- BPDU (Bridge Protocol Data Units) : Trames échangées entre les switches via le protocole Spanning Tree (STP) pour détecter et empêcher les boucles réseau.
- CPL (Courant Porteur en Ligne) : Technologie permettant de faire transiter des données informatiques via le réseau électrique existant d'un bâtiment.
- Ad-hoc : Mode de connexion réseau sans fil permettant à deux appareils de communiquer directement entre eux sans passer par un point d'accès central.
#### Systèmes, Virtualisation et Stockage
- PXE (Preboot Execution Environment) : Protocole permettant à un ordinateur de démarrer depuis le réseau en téléchargeant un système d'exploitation ou un outil de diagnostic depuis un serveur central.
- VDI (Virtual Desktop Infrastructure) : Technologie consistant à héberger des bureaux utilisateurs sur des machines virtuelles centralisées dans un datacenter, accessibles à distance.
- Openstack : Plateforme logicielle libre utilisée pour construire et gérer des infrastructures de Cloud Computing (IaaS).
- FreeNas (TrueNAS) : Système d'exploitation open source permettant de transformer un ordinateur en serveur de stockage réseau (NAS).
- Cluster : Groupe de plusieurs serveurs physiques travaillant ensemble pour assurer la haute disponibilité (HA) ou la répartition de charge.
- OVA / OVF : Formats de fichiers standards utilisés pour exporter et importer des machines virtuelles entre différents hyperviseurs.
- VMS : Souvent "Virtual Management System" (gestionnaire de VMs comme vCenter) ou "Video Management Software" (gestion de vidéosurveillance).
- Appliance : Solution prête à l'emploi (matérielle ou virtuelle) combinant un OS et un logiciel optimisés pour une tâche spécifique (ex: appliance de sauvegarde).
- iSCSI : Protocole permettant de transporter des commandes de stockage SCSI sur un réseau IP (TCP/IP).
	- iSCSI Target : Le serveur ou la baie de stockage qui "partage" le disque sur le réseau.
	- iSCSI Initiator : Le client (serveur/ordinateur) qui se connecte à la cible pour utiliser le disque distant comme s'il était local.
- LUN (Logical Unit Number) : Identifiant d'une unité de stockage logique (partition d'une baie SAN) présentée à un serveur.
- Datastore : Conteneur de stockage logique (banque de données) utilisé par un hyperviseur pour stocker les fichiers des machines virtuelles.
- VNIC ou VMIC : Carte d'interface réseau virtuelle assignée à une machine virtuelle pour la relier au commutateur virtuel.
- Sur-allocation (Overcommitment) : Pratique consistant à allouer plus de ressources virtuelles (CPU, RAM) que les ressources physiques réellement disponibles sur l'hôte.
- CPU Ready : Indicateur de performance montrant le temps durant lequel une VM attend que l'hyperviseur lui accorde du temps processeur physique pour s'exécuter.
- DPM (Distributed Power Management) : Fonctionnalité (notamment VMware) qui éteint les hôtes inutilisés d'un cluster pour économiser l'énergie en déplaçant les VMs sur les autres hôtes.
- Déploiement : Processus d'installation automatisée de logiciels ou de systèmes sur de multiples postes. L'objectif est d'assurer une configuration uniforme et rapide de l'ensemble du parc.
#### Sécurité et Administration
- ACL (Access Control List) : Liste de règles configurées sur un équipement réseau (routeur/firewall) pour autoriser ou bloquer le trafic selon des critères (IP, port, protocole).
- Pfsense : Distribution logicielle open source basée sur FreeBSD, largement utilisée comme pare-feu et routeur.
- Failover (Bascule) : Mécanisme de sécurité qui redirige automatiquement le trafic ou les services vers un système de secours en cas de panne du système principal.
- RSAT (Remote Server Administration Tools) : Outils Microsoft permettant de gérer des rôles Windows Server (AD, DHCP, DNS) depuis un poste client.
- ACME : Protocole automatisé (utilisé par Let's Encrypt) pour la demande, le renouvellement et l'installation de certificats SSL/TLS.
- Disque pass-through : Configuration permettant à une VM d'accéder directement à un disque physique de l'hôte sans passer par le système de fichiers de l'hyperviseur.
- Load-balancing : Répartition de la charge de travail entre plusieurs serveurs. Cela évite la saturation d'une seule machine et améliore la rapidité de réponse.
#### Méthodologie et RSE (Responsabilité Sociétale des Entreprises)
- Infogérance : Externalisation de la gestion du système d'information à un prestataire spécialisé (MSP).
	- Sur site : Le technicien intervient physiquement dans l'entreprise.
	- Hors site : Le système est géré à distance (Cloud ou télégestion).
- Veille technologique : Activité consistant à s'informer régulièrement des nouveautés techniques pour anticiper les évolutions et rester compétent.
- Loi AGEC : Loi anti-gaspillage pour une économie circulaire, imposant notamment des indices de réparabilité sur le matériel informatique.
- GES (Gaz à Effet de Serre) : Mesure de l'impact carbone de l'infrastructure informatique (consommation électrique, fabrication).
- DEEE : Déchets d'Équipements Électriques et Électroniques. Matériels en fin de vie devant suivre une filière de recyclage spécifique.
- INR : Institut du Numérique Responsable, qui promeut la réduction de l'empreinte environnementale du numérique.
- ODD : Objectifs de Développement Durable définis par l'ONU.
- QQOQCCP : Méthode d'analyse (Quoi, Qui, Où, Quand, Comment, Combien, Pourquoi) utilisée pour diagnostiquer un incident ou définir un besoin client.
- BigData : Ensembles de données si volumineux qu'ils nécessitent des outils de traitement spécifiques (les "3V" : Volume, Variété, Vélocité).
- Infrastructure :
	- Locale : Dans les locaux de l'entreprise (On-premise).
	- Distante : Hébergée dans un datacenter tiers ou dans le Cloud.
	- Physique : Matériels réels (serveurs, baies).
	- Virtuelle : Ressources simulées par un hyperviseur.
#### 
SAN
(Storage Area network) est un réseau spécialisé permettant de mutualiser des ressources de stockage.

#### Latence
la latence (ou délai de transit, ou retard) est le délai de transmission dans les communications informatiques [1] (on trouve souvent l’anglicisme lag).
Il désigne le temps nécessaire à un paquet de données pour passer de la source à la destination à travers un réseau.
#### RTP
Real-Time Transport Protocol (RTP) est un protocole de communication informatique permettant le transport de données soumises à des contraintes de temps réel, tels que des flux média audio ou vidéo
#### 
STP
Le Spanning Tree Protocol (RSTP rapid, MSTP multiple) est un protocole réseau de niveau 2 permettant de déterminer une topologie réseau sans boucle (appelée algorithme de l' arbre recouvrant) dans les LAN avec ponts. Il est défini dans la norme IEEE 802.1D et est basé sur un algorithme décrit par Radia Perlman en 1985[1].
#### 
LLDP
Link Layer Discovery Protocol (LLDP) est un protocole de communication décrit par les standards IEEE 802.1 AB et IEEE 802.3 (clause 79). Il permet aux équipements de réseau d'échanger leurs identités et leurs capacités ( autonégociation, taille de trame maximale, etc.) sur un réseau local, le plus souvent un réseau Ethernet, et ainsi de découvrir la topologie du réseau de proche en proche.
#### CEPH
Ceph est une solution libre de stockage distribué (software-defined storage) qui propose trois protocoles en un avec : Bloc, Fichiers & Objet (S3). Les objectifs principaux de Ceph sont d'être complètement distribués sans point unique de défaillance, extensible jusqu'à l' exaoctet et librement disponible. Les données sont répliquées, permettant au système d'être tolérant aux pannes.

#### Systèmes et réseaux
			Caractéristique
			Système (Host)
			Réseau (Infrastructure)
			Rôle principal
			Exécuter des tâches et stocker des données.
			Transporter les données d'un point A à un point B.
			Focus
			L'utilisateur et ses applications (ex: mail, fichier).
			La connectivité et la disponibilité du chemin.
			Exemple de métier
			Administrateur Système : gère les comptes AD, installe les serveurs.
			Administrateur Réseau : configure les switches et sécurise le Firewall.
			Référence modèle OSI
			Principalement les couches hautes (5 à 7).
			Principalement les couches basses (1 à 4).
#### 
Cloud (Computing) :


Exemples d'offres : 
- Azure : Microsoft
- Cisco
- AWS : Amazon web service

#### On premise
Infrastructure entièrement en local, matériel complètement géré par l'entreprise utilisatrice
#### 
IaaS
Infrastructure as a service, Architecture cloud/Infrastructure informatique cloud (serveurs, stockage, sauvegarde, réseau) Matériel géré par le fournisseur de service, Administration par le client (Ex: AWS, Azure VM, Google compute engine, Digital Ocean)
#### 
SaaS
Software as a service, Applications cloud. Applications installés sur serveur distant, sur le web, sous forme de site web ou service.
#### 
PaaS
Platform as a service, Services hébergés/cloud. Services/Applications géré par le client et plateforme (matériel, système, réseau, stockage) d'exécution géré par le fournisseur (Ex: Google App engine, Azure App service, Heroku)

#### CLI
Interface en ligne de commande
#### 
GUI
Interface utilisateur graphique

#### Open source

### Organisation (SI)

SI (Système d'Information) : Ensemble organisé de ressources (matériel, logiciels, personnel, données) permettant de collecter, stocker et traiter l'information d'une entreprise. Il ne se limite pas à l'informatique mais englobe tous les flux de données métiers.
CDS (Centre de Services / Service Desk) : Point de contact unique (SPOC) entre les utilisateurs et la direction informatique. Il gère les incidents et les demandes de services en suivant les bonnes pratiques ITIL.

Support Client : Un support client est une ressource centralisée élaborée pour apporter à l'utilisateur interne ou au client des informations, du support relié aux processus, des produits ainsi que des services de l'entreprise.

Centre d'appels : Un centre d'appels/centre de contacts permet de gérer les contacts et les clients. Le bureau a pour mission de gérer une grande capacité de demandes, principalement par téléphone (les demandes peuvent se faire aussi par lettres, messagerie instantanée, e-mails, réseaux sociaux ou fax). Les centres d'appels entrants sont fréquemment employés pour le service client, le service téléphonique 24h/24 7j/7, le traitement de commandes et le support produit. Les centres d'appels sortants sont employés pour les études de marché, le télémarketing, le recouvrement de créances, etc. Une entreprise peut détenir de multiples centres d'appels qui permettent de prendre en charge divers aspects des opérations business. Ils peuvent être dirigés en interne ou par un sous-traitant.

Helpdesk : Centre d'assistance (ou Centre de Services)
- Niveau 1 : Centre d'appel, assistance pour les sujets les plus courants
- Niveau 2 : "Back desk", personnel plus technique, gestion des sujets plus complexes / technique
- Niveau 3 : Assistance par des techniciens spécialistes, interne ou externe

Niveaux d'assistance informatique :
- Niveau 0 : Informations, forums, base de connaissances, ...
- Niveau 1 : Support informatique
- Niveau 2 : Support intermédiaire, résolution de problème et analyse, aide et documentation pour les niveaux 0, 1
- Niveau 3 : Support expert, résolution de problèmes majeurs, encadres et gère les tickets, aide et documentation pour les niveaux 0, 1 et 2
- Niveau 4 : Support externe, garantie
Escalade

Niveaux de gravité : 
- Gravité 1 : Incident critique ayant un impact très important. Il s'agit souvent d'une panne complète du système, d'une perte de données des clients, d'une atteinte majeure à la sécurité ou d'une défaillance d'une infrastructure essentielle.
- Gravité 2 : Incident majeur ayant un impact important. Il peut s'agir d'une interruption partielle du système ou d'une atteinte à des fonctionnalités essentielles.
- Gravité 3 : Incident modéré avec un impact modéré qui peut affecter des fonctionnalités non critiques ou causer des désagréments aux utilisateurs.
- Gravité 4 : Incident mineur ayant un faible impact et pouvant inclure des dysfonctionnements de fonctions non critiques ou des plaintes d'utilisateurs de faible priorité.
- Gravité 5 : Défaut de bas niveau ayant un impact très faible. Ces demandes ne sont pas associées à une perturbation ou à un impact immédiat sur les activités de l'entreprise.

Gestion des incidents : La gestion des incidents (IM) ITIL consiste à restaurer les services le plus rapidement possible après un incident. C'est aussi un composant principal du support de service ITIL.

Incident : (coupure de service) Un incident peut être défini comme tout événement imprévu qui perturbe ou interrompt le fonctionnement normal d’un service informatique. Il s’agit généralement d’un incident isolé, ponctuel et de courte durée. Une panne de réseau, un ordinateur qui ne démarre pas ou un logiciel qui se bloque sont tous des exemples d’incidents. Les incidents sont souvent signalés par les utilisateurs ou détectés par les outils de surveillance des systèmes.
- technique (anomalie du logiciel ou problème d'exploitation),
- fonctionnel (adéquation aux besoins des utilisateurs),
- réglementaire (compréhension des règles de gestion).

Problème : (cause des coupures de service) un problème est une cause sous-jacente ou une origine récurrente qui provoque un ou plusieurs incidents. Contrairement aux incidents, les problèmes ne sont pas des événements isolés. Il s’agit de situations qui nécessitent une analyse approfondie pour identifier les causes fondamentales. Par exemple, si un logiciel spécifique cesse de fonctionner régulièrement, cela peut être considéré comme un problème. En effet, il y a une cause sous-jacente qui doit être identifiée et résolue pour prévenir les incidents futurs.

Les 3 Phases de gestion des problèmes :
- Identification des problèmes
- Contrôle des problèmes
- Contrôle des erreurs

Solution de contournement
Une solution de contournement est définie comme une solution qui réduit ou élimine l'impact ou la probabilité d'un incident ou d'un problème pour lequel une résolution complète n'est pas encore disponible.

CRM (Gestion de la Relation Client) : Logiciel centralisant toutes les interactions entre une entreprise et ses clients. Il permet de suivre l'historique des échanges, les ventes et d'améliorer la satisfaction client.
Méthode CERC : Technique de communication en support client (Contact, Écoute, Raison, Conclusion). Elle structure l'appel pour garantir un accueil pro, un diagnostic précis et une clôture de ticket validée par l'utilisateur.

Gestion des services d'assistance : Issue Tracking System et ServiceDesk
Outils logiciels (ex: GLPI, Jira) permettant de créer, suivre et historiser des tickets d'assistance. Ils sont indispensables pour mesurer l'activité du support et respecter les délais de résolution.

DSI (Direction des Systèmes d'Information) : Entité ou personne responsable de la stratégie, de la conception et de l'évolution du parc informatique. Elle aligne les moyens technologiques sur les besoins stratégiques de l'entreprise.
RSSI (Responsable Sécurité SI) : Expert chargé de définir et d'appliquer la politique de sécurité (PSSI). Il garantit le respect du cycle DICT : Disponibilité, Intégrité, Confidentialité et Traçabilité des données.
ESN (Entreprise de Service Numérique) : Société spécialisée fournissant des prestations informatiques (conseil, développement, maintenance) à d'autres entreprises. C'est le nouveau nom des anciennes SSII.
ISP / FAI : Organisme (ex: Orange, Free, SFR) fournissant la connexion technique au réseau Internet. Il loue ou gère les infrastructures de transport (fibre, cuivre, 4G/5G).
ERP (PGI) : Logiciel de gestion intégré qui regroupe tous les services de l'entreprise (compta, RH, stocks, ventes) dans une base de données unique. Cela permet d'unifier les informations et d'automatiser les processus métiers.

Intranet: L'Intranet est un réseau privé interne réservé aux employés.

Extranet:  L'Extranet est une extension sécurisée de ce réseau ouverte à des partenaires extérieurs (fournisseurs, clients). 

BYOD: Bring your own device, utilisation de terminaux personnels pour une utilisation en entreprise et d'autres cas

PSSI : politique de sécurité des systèmes d'information, c'est un plan d'action défini pour maintenir un certain niveau de sécurité. Elle reflète la vision stratégique de la direction de l'organisme (PME, PMI, industrie, administration, État, union d'États…) en matière de sécurité des systèmes d'information (SSI)

Charte de sécurité informatique : Document juridique et technique définissant les règles de bon usage des outils informatiques par les employés. Elle précise les responsabilités de chacun et les sanctions en cas de non-respect.

RGPD : Règlement général sur la protection des données (GDPR en anglais, General Data Protection Regulation). Teste de loi pour protéger et réguler les données informatique personnel des citoyens européens

ITIL : Information Technology Infrastructure Library, Bibliothèque pour l'infrastructure des technologies de l'information. Ensemble d'ouvrages recensant les bonnes pratiques de la gestion des produits et services informatiques et numériques.
			Terme
			Définition
			Activité
			Ensemble d'actions permettant d'obtenir un résultat spécifique. Les activités se définissent habituellement comme des parties de processus ou de plans et sont documentées dans des procédures.
			Client
			Terme générique désignant la clientèle, le business ou un client du business.
			Escalade fonctionnelle
			Action de transférer un incident, un problème ou un changement à une équipe technique possédant un plus haut degré d'expertise afin d'aider le processus d'escalade.
			Escalade hiérarchique
			Informer ou impliquer des niveaux plus seniors du management afin d'aider le processus d'escalade.
			Fonction
			Équipe ou groupe de personnes ainsi que les outils et ressources qu'ils utilisent pour mener à bien un ou plusieurs processus ou activités (ex. : Centre de services).
			Heures de support
			Heures auxquelles l’assistance est disponible pour les utilisateurs. Normalement ce sont les horaires d’ouverture du Centre de Services. Les heures de support doivent être définies dans un accord sur les niveaux de service et peut être différentes des heures de service. Par exemple, les heures de service peuvent être 24h/24 et les heures de support seront 7h00 à 19h00.
			Impact
			Mesure de l'effet d'un incident, problème ou changement sur les processus d'affaires. L'impact est souvent basé sur la manière dont les niveaux de service seront affectés. L'impact et l'urgence servent à assigner une priorité.
			ITIL®
			ITIL® (Information Technology Infrastructure Library / Bibliothèque d’Infrastructure des Technologies de l’Information) est un cadre de référence des bonnes pratiques dans la gestion des services informatiques. Il fournit des orientations sur une prestation de services informatiques de qualité, sur les processus, les fonctions et autres aptitudes requises pour les soutenir.
			Point de contact unique
			Fournit un moyen unique et cohérent de communiquer avec une organisation ou une unité d'affaires. Par exemple, le point de contact unique d’un fournisseur deservice informatique est habituellement appelé Centre de Services.
			Priorité
			Catégorie servant à identifier l'importance relative d'un incident, d'un problème ou d'un changement. La priorité est basée sur l'impact et l'urgence et sert à identifier le délai acceptable pour réaliser une action. Par exemple, l'accord sur les niveaux de service peut statuer que les incidents de priorité 2 doivent être résolus en 12 heures.
			Processus
			Ensemble d'activités structurées conçues pour atteindre un objectif spécifique. Un processus traite une ou plusieurs entrées (input) et les transforme en résultats (output). Un processus peut inclure la définition des rôles, responsabilités, outils et contrôles de gestion nécessaires à la fourniture de résultats de manière fiable. Un processus peut définir des politiques, des activités et des instructions de travail si nécessaire.
			Résolution
			Action de réparer la cause première d'un incident ou d'un problème ou d'implanter une solution de contournement.
			Rôle
			Ensemble de responsabilités, d'activités et d'autorités attribuées à une personne ou à une équipe. Le rôle est défini dans un processus ou une fonction. Une personne ou une équipe peut avoir plusieurs rôles, à condition qu'ils ne soient pas antagonistes. Le terme rôle signifie également le but ou l'utilisation de quelque chose.
			Service informatique
			Moyen de fournir de la valeur à des clients en facilitant les résultats qu'ils veulent obtenir sans qu'ils aient la propriété des coûts ou des risques.
			Urgence
			Mesure du temps que met un incident, un problème ou un changement à avoir un impact significatif sur le business. Par exemple, un incident à fort impact peut avoir une urgence faible, si cet impact n’affecte pas les affaires avant la fin de l’exercice financier. L'impact et urgence servent à attribuer un niveaude priorité.
			Utilisateur
			Personne qui utilise quotidiennement un service informatique. Les utilisateurs se distinguent des clients, car certains clients n'utilisent pas directement le service informatique.

			Centre de services
			Point de contact unique entre le fournisseur de services et les utilisateurs. Un centre de services typique gère les incidents et les demandes de service, ainsi que les communications avec les utilisateurs.
			Escalade
			Activité visant à obtenir des ressources supplémentaires afin d'atteindre les cibles de niveaux de service ou satisfaire les attentes du client. Il y a deux types d'escalade : escalade fonctionnelle et escalade hiérarchique.
			Gestion des incidents
			Processus responsable de la gestion du cycle de vie de tous les incidents. La gestion des incidents s'assure que l'exploitation normale des services soit rétablie le plus rapidement possible et que l'impact sur le business soit réduit au minimum.
			Incident
			Interruption non planifiée ou réduction de la qualité d'un service informatique. La défaillance d'un élément de configuration (CI) qui n'a pas encore eu d'impact sur le service est aussi un incident.
			Incident majeur
			Plus haute catégorie d'impact pour un incident. Un incident majeur provoque une interruption significative des affaires.
			Premier, deuxième ou xième niveau de support
			Premier, deuxième ou xième niveau dans la hiérarchie des groupes de support impliqués dans la résolution des incidents. Chaque niveau contient un niveau de compétences plus élevé ou dispose de davantage de temps ou de ressources.

			Demande de service (SR)
			Demande formelle d'un utilisateur pour quelque chose devant être fournie, par exemple, une demande d'information ou des conseils; pour réinitialiser un mot de passe ou pour installer un poste de travail pour un nouvel utilisateur. Les demandes de service sont gérées par le processus d’Exécution des Requêtes, habituellement en conjonction avec le Centre de Services.
			Exécution des requêtes
			Processus responsable de la gestion du cycle de vie de toutes les demandes de service.
			Modèle de requête
			Façon reproductible de traiter une catégorie particulière de demande de service. Un modèle de requête définit les étapes spécifiques convenues qui seront suivies pour une demande de service de cette catégorie. Il peut être très simple, sans exigence d'autorisation, ou être plus complexe avec de nombreuses étapes qui nécessitent une autorisation.
			Erreur connue
			Problème pour lequel il existe une cause première et une solution de contournement documentées. Les erreurs connues sont créées et gérées tout au long de leur cycle de vie par la Gestion des Problèmes.
			Gestion des problèmes
			Processus responsable de la gestion du cycle de vie de tous les problèmes. La Gestion des Problèmes prévient proactivement que des incidents ne surviennent et minimise l’impact des incidents qui ne pourraient pas être évités.
			Gestion proactive des problèmes
			Fait partie du processus de Gestion des problèmes. L'objectif est d'identifier et traiter les causes potentielles d'incidents avant qu'ils ne surviennent. Elleanalyse les enregistrements d’incidents et utilise les données collectées par les autres processus de gestion des services informatiques pour identifier les tendances ou les problèmes significatifs.
			Problème
			Cause d’un ou de plusieurs incidents. Cette cause n’est pas forcément connue au moment de l’enregistrement d’un problème et le processus de Gestion des Problèmes est alors chargé d'investiguer.
			Solution de contournement
			Réduire ou éliminer l’impact d’un incident ou d’un problème pour lequel une résolution complète n’est pas encore disponible. Par exemple, en redémarrant un élément de configuration défaillant. Les solutions de contournement des problèmes sont documentées dans les enregistrements d’erreurs connues. Les solutions de contournement des incidents qui n’ont pas été associées aux problèmes sont documentées dans les incidents.
			Calendrier des changements
			Document fournissant la liste des changements autorisés et leurs dates d’implantation prévues, aussi bien que les dates prévues des changements à long terme. Un calendrier des changements est parfois appelé calendrier prévisionnel des changements, bien qu’il contienne également des informations sur les changements déjà implantés.
			Changement
			Ajout, modification ou suppression de tout ce qui peut avoir un effet sur les services informatiques. Le périmètre doit inclure les changements aux architectures, aux processus, aux outils, aux métriques et à la documentation aussi bien que les changements aux services informatiques et aux autres éléments de configuration.
			Changement normal
			Changement qui n'est ni un changement urgent ni un changement standard. Un changement normal suit les étapes prédéfinies du processus de Gestion des changements.
			Changement standard
			Changement préautorisé présentant peu de risque, relativement commun et qui sera exécuté selon une procédure ou une instruction de travail. Par exemple, la réinitialisation d’un mot de passe ou la fourniture d’un équipement standard à unnouvel employé. Des demandes de changement (RFC) ne sont pas requises pour implanter un changement standard, car celles-ci sont journalisées et suivies selon un mécanisme différent, tel qu’une demande de service.
			Changement urgent
			Changement qui doit être mis en œuvre dès que possible. Par exemple, pour résoudre un incident majeur ou implémenter un correctif de sécurité. Le processus de Gestion des Changements aura normalement une procédure spécifique pour traiter les changements urgents.
			Comité consultatif sur les changements (CAB)
			Groupe de personnes qui apporte un appui à l’évaluation, la définition des priorités, les autorisations et la planification des changements. Le comité consultatif sur les changements est habituellement composé de représentants de tous les domaines au sein du fournisseur de service informatique, du business et des tierces parties telles que les fournisseurs externes.
			Comité consultatif sur les changements urgents (ECAB)
			Sous-groupe du comité consultatif sur les changements qui prend les décisions concernant les changements urgents. Le choix des membres de l’ECAB peut être fait au moment de la convocation, et dépend de la nature du changement urgent.
			Demande de changement (RFC)
			Demande formelle de changement à effectuer. Une RFC comporte des détails sur le changement proposé et peut être enregistrée sur papier ou électroniquement. Le terme RFC est souvent utilisé à contresens pour signifier un enregistrement d’un changement ou le changement lui-même.
			Gestion des changements
			Processus responsable de contrôler le cycle de vie de tous les changements, facilitant la réalisation de changements bénéfiques avec un minimum d’interruption des services informatiques.
			Modèle de changement
			Manière répétitive de traiter une catégorie particulière de changements. Un modèle de changement établit des étapes spécifiques prédéfinies qui seront suivies pour réaliser un changement de cette catégorie. Les modèles de changement peuvent être très complexes avec plusieurs étapes nécessitant une autorisation (par exemple, une mise en production logicielle majeure) ou êtretrès simples sans besoin d’autorisation (par exemple, la réinitialisation d’un mot de passe).
			Retour arrière
			Activité qui rétablit un service ou un autre élément de configuration dans un état correspondant à une base de référence antérieure. Le retour arrière est utilisécomme une forme de rattrapage lorsqu’un changement ou une mise en production n’a pas été couronné de succès.
			Actif de service
			Ressource ou capacité pouvant contribuer à la livraison d'un service. Un actif de service pourrait inclure, par exemple, un serveur virtuel, un serveur physique, une licence logicielle, de l'information stockée dans un système de gestion des services, ou toute connaissance dans la tête d'un gestionnaire senior.
			Attribut
			Information concernant un élément de configuration. Les attributs des éléments de configuration sont enregistrés dans la base de données de gestion des configurations (CMDB).
			Base de données de gestion des configurations (CMDB)
			Base de données servant à stocker les enregistrements d'une configuration tout au long de son cycle de vie. Elle regroupe les attributs des éléments de configuration (CI) et les liens avec les autres CI. CMDB veut dire Configuration Management Data Base.
			Élément de configuration (CI)
			Tout composant ou actif de service qui participe à la gestion d'un service TI et qui nécessite d'être géré. Les informations concernant chacun des CI sont enregistrées dans l'enregistrement d'une configuration au sein d'un système de gestion des configurations où elles sont tenues à jour pendant tout le cycle de vie par la Gestion des Actifs de Service et des Configurations. Les éléments de configurations sont sous le contrôle de la Gestion des Changements. Ils comprennent habituellement les services informatiques, le matériel, les logiciels, les immeubles, les personnes et la documentation formelle telle que la documentation des processus et les accords sur les niveaux de service.
			Enregistrement de configuration
			Ensemble d'attributs et de relations propres à un CI. Les enregistrements de configuration sont stockés dans la base de données de gestion des configurations (CMDB). Noter que les enregistrements de configuration décrivant les CIs sont stockés dans une CMDB et non pas les CIs eux-mêmes.
			Gestion des actifs
			Activité ou processus générique responsable du suivi et de la production des rapports sur la valeur et la propriété des actifs financiers tout au long de leur cycle de vie.
			Gestion des actifs de service et des configurations
			Processus responsable d'assurer que les actifs nécessaires à la prestation des services sont bien contrôlés et que l’information sur ces actifs est exacte, fiable et disponible quand et où elle est nécessaire. Cette information comprend des détails sur la manière dont les actifs ont été configurés et les relations entre les actifs.
			Type de CI
			Catégorie servant à classer les éléments de configuration. Le type de CI identifie les attributs et les relations requis pour un enregistrement d’une configuration. Les types de CI les plus répandus sont : matériel, logiciel, document, etc.
			Entente sur les niveaux de service (SLA)
			Accord entre un fournisseur de service informatique et un client. L’accord sur les niveaux de service décrit le service informatique, documente les cibles de niveau de service et spécifie les responsabilités du fournisseur de service informatique et du client.
			Gestion des niveaux de service
			Processus responsable de négocier les accords sur les niveaux de service réalisables et de s’assurer qu’ils sont atteints. La gestion des niveaux de service doit s’assurer également que tous les processus de gestion des servicesinformatiques, les accords sur les niveaux opérationnels et les contrats de sous-traitance sont adaptés aux cibles de niveau de service. Elle surveille et établit des rapports sur les niveaux de service, organise régulièrement des revues avec les clients et identifie les améliorations requises.
			Alerte
			Avertissement qu'un seuil a été atteint, que quelque chose a changé ou qu'une défaillance s'est produite. Les alertes sont souvent créées et gérées par les outils de gestion des systèmes.
			Événement
			Changement d'état significatif d'un service TI ou de tout autre élément de configuration. Le terme événement est aussi employé pour désigner une alerte ou une notification créée par un service informatique, un élément de configuration ou un outil de surveillance.
			Gestion des événements
			Processus responsable de la gestion des événements tout au long de leur cycle de vie.
			Surveillance
			Observation répétée de l'état d'un élément de configuration (CI), d'un service informatique ou d'un processus afin de détecter les événements et de s'assurer que son état réel est connu.
			Surveillance proactive
			Type de supervision basé sur des modèles d’enchaînement d’événements permettant d’anticiper d’éventuelles défaillances.
			Surveillance réactive
			Supervision prenant les mesures adéquates en fonction d’un événement. Par exemple, soumettre une tâche par lot lorsque la tâche précédente est terminéeou journaliser un incident lorsqu’une erreur s’est produite.

Niveau des membre d'une organisation ITIL :

			Informatique
			Métier
			Stratégique
			L'équipe de management (CIO)
			L'équipe de management (CEO)
			Tactique
			Gestion des niveaux de services
			Les clients
			Opérationnel
			Support technique
			Les utilisateurs
Cycle de vie d'un ticket ITIL
			Phase du ticket
			Phase
			Action clé
			Cycle de vie du ticket
			Créé
			Détection / Enregistrement
			Identification
			Un problème ou une demande est identifié(e) par l’utilisateur, le centre d’assistance ou un outil de monitoring. Le ticket est créé dans le système de gestion des incidents avec les informations de base (qui, quoi, quand, où).
			Créé
			Classification / Priorisation
			Catégorisation / Niveau d'urgence
			Le ticket est catégorisé (type d’incident, service concerné, composant) et priorisé (impact + urgence). Cette classification permet de choisir le bon processus de traitement et d’établir les SLA appropriés.
			Affecté
			Attribution
			Transmission
			Le ticket est assigné à l’équipe ou à la personne la mieux placée pour le résoudre (premier niveau, deuxième niveau, groupe spécialisé). Si aucune ressource adéquate n’est disponible, le ticket peut être escaladé.
			(Affecté)
			(Escalade, si nécessaire)
			(Transmission)
			Si le ticket ne peut pas être résolu au niveau actuel (manque de compétences, besoin d’autorisation, impact élevé), il est escaladé vers un niveau supérieur ou un groupe spécialisé.
			En cours (de résolution)
			Diagnostic / Analyse
			Analyse
			L’analyste examine les détails, reproduit le problème, collecte des logs ou des informations complémentaires et identifie la cause première. Cette phase peut inclure des recherches dans la base de connaissances ou des tests.
			Résolu
			Résolution
			Mise en œuvre
			Une fois la cause identifiée, une solution est mise en œuvre (correction, contournement, mise à jour, etc.). La solution est documentée dans le ticket pour référence future.
			Clos
			Clôture
			Vérification
			L’utilisateur confirme que le problème est résolu et que le service fonctionne comme attendu. Si la validation échoue, le ticket revient à l’étape de diagnostic.
			Archivé
			Archivage
			Partage de l'information 
			Le ticket est officiellement fermé. Toutes les informations pertinentes (cause, actions, temps passé, leçons apprises) sont archivées afin d’alimenter la base de connaissances et les rapports de performance.
ITSM Information Technology Service Management / Gestion des services informatiques. 
Ensemble de pratiques visant à fournir des services informatiques de qualité et alignés sur les besoins des clients. ITIL est le cadre de référence le plus utilisé pour l'ITSM.
Exemple de logiciels ITSM :
- GLPI : Gestionnaire libre de parc informatique
- Zendesk
- Jira (Service Management)

### Contrats de service 

QoS (Qualité de Service) : Capacité d'un réseau à prioriser certains flux de données par rapport à d'autres (ex: la voix sur IP est prioritaire sur un téléchargement). Cela garantit la fluidité des services critiques même en cas de saturation.

PRA (Plan de restauration d'activité)
Le PRA (Restauration) définit les étapes pour relancer le SI après un sinistre majeur.

PCA (Plan de continuité d'activité)
Le PCA (Continuité) prévoit les moyens pour que le service ne s'arrête jamais, même en cas de panne.

SLA: Service Level Agreement ou Accord de Niveau de Service
Contrat entre un prestataire et un client définissant le niveau de qualité attendu (disponibilité, délais). Il inclut souvent des pénalités financières si les objectifs ne sont pas atteints.

HA : High availability
Architecture conçue pour minimiser les interruptions de service, souvent par redondance des équipements. On la mesure en "nombre de 9" (ex: 99,99% de disponibilité).

FT : Fault tolerance est une fonction qui protège une machine virtuelle contre la défaillance matérielle du serveur hôte. Niveau de protection supérieur où le système continue de fonctionner sans aucune interruption même en cas de panne matérielle totale d'un composant. Contrairement à la HA, il n'y a aucun temps de bascule ou de redémarrage.

Uptime
Durée de fonctionnement ininterrompu d'un serveur ou d'un équipement depuis son dernier démarrage. C'est un indicateur clé de la stabilité d'un système.

GTI : Garantie de temps d'intervention
La GTI est le délai maximum pour que le technicien commence à travailler sur la panne. 

GTR : Garantie de temps de rétablissement
La GTR est le délai maximum contractuel pour que le service soit de nouveau opérationnel.

### Organismes

ANSSI : Agence Nationale de la Sécurité des Systèmes d’Information

IEEE: Institute of Electrical and Electronics Engineers, en français : Institut des Ingénieurs Électriciens et Électroniciens

EIA : Electronic Industries Alliance. Cette organisation est surtout connue pour ses normes relatives au câblage électrique, aux connecteurs et aux racks de 19 pouces utilisés pour monter les équipements de réseau.

TIA : Telecommunications Industry Association. Organisation responsable de l'élaboration de normes de communication dans divers domaines, notamment les équipements radio, les tours de téléphonie cellulaire, les dispositifs de voix sur IP (VoIP), les communications par satellite, etc. La figure montre un exemple de câble Ethernet certifié qui a été développé en coopération par la TIA et l'EIA.

UIT-T : Union internationale des télécommunications, Secteur de la normalisation des télécommunications. L'une des plus grandes et des plus anciennes organisations de normalisation des communications. L'ITU-T définit des normes de compression vidéo, de télévision sur IP (IPTV) et de communication haut débit, comme la DSL (digital subscriber line ou ligne d'abonné numérique).

ISOC : Internet Society. Responsable de la promotion du développement ouvert et de l'évolution de l'utilisation de l'internet dans le monde entier.

IAB : Internet Architecture Board. Responsable de la gestion globale et du développement des normes Internet.

IETF : Internet Engineering Task Force. Développe, met à jour et assure la maintenance des technologies Internet et TCP/IP. Cela inclut le processus et les documents pour le développement de nouveaux protocoles et la mise à jour des protocoles existants, qui sont connus sous le nom de documents de demande de commentaires (RFC).

IRTF : Internet Research Task Force. Se concentre sur la recherche à long terme liée à l'internet et aux protocoles TCP/IP comme l'Anti-Spam Research Group (ASRG), le Crypto Forum Research Group (CFRG) et le Peer-to-Peer Research Group (P2PRG).

### Réseau
Un protocole : Un protocole se constitue d'un ensemble de règles et de procédures qu'il faut respecter afin de permettre l'autorisation de la communication entre plusieurs ordinateurs échangeant des données.

Modèle OSI : Open Systems Interconnection ou modèle pour l’interconnexion de systèmes ouverts. Norme et modèle de communication en réseau, de tous les systèmes informatiques (proposé par l'ISO, organisation internationale de normalisation)
On part de la couche 7 (Haut) vers la couche 1 (Bas) :
Après Plusieurs Semaines, Tout Revient Logiquement Physique.
			Couche
			Nom
			Rôle principal
			PDU (Unité)
			Équipement / Protocole
			7
			Application
			Interface utilisateur
			Données
			HTTP, FTP, DNS, DHCP
			6
			Présentation
			Formatage, Chiffrement
			Données
			JPG, MP4, SSL/TLS, HTML
			5
			Session
			Dialogue entre machines
			Données
			NetBIOS, RPC
			4
			Transport
			Connexion de bout en bout
			Segment TCP, Datagramme UDP
			TCP, UDP
			3
			Réseau
			Adressage IP et Routage
			Paquet IP
			Routeur, IP, ICMP
			2
			Liaison de données
			Adressage MAC
			Trame (MAC, LLC)
			Switch, WiFi, Ethernet
			1
			Physique
			Transmission binaire
			Bits (analogique ou numérique)
			Câbles, Hub, Signaux

TCP Tranmission Control Protocol (connecté): Protocole de contrôle de transmission
TCP est un protocole fiable qui vérifie que les données arrivent bien et dans l'ordre.

Protocoles : 
- Mail, SMTP
- Fichiers, FTP
- Session à distance, SSH
- Web, HTTP
- Bits de contrôle TCP :
	- URG: Pointer urgent significatif, ACK : accusé de réception/validation, PSH : fonction push, RST : réinitialisation de la connexion, SYN : synchronisation/connexion, FIN : Fin des donnés à transmettre

TCP/IP: Transmission control protocol (Protocole de communication permettant de rattacher des machines entre elles)
Modèle de référence et suite de protocoles universels utilisés pour la communication sur Internet et les réseaux locaux. Il structure l'échange de données en 4 couches :
- 4 Application (Couche OSI 7, 6, 5)
- 3 Transport (Couche OSI 4)
- 2 Internet/Réseau (Couche OSI 3)
- 1 Accès au réseau (Couche OSI 2, 1)

Ports TCP/IP : sur 16 bits de 0 à 65535
- 0 à 1023 : ports connus
- 1024 à 49151 : ports inscrits
- 49152 à 65535 : ports privés/réservés (ports éphémères)

UDP User Datagram Protocol (non connecté) : Protocole de Datagramme utilisateur
UDP est plus rapide car il n'attend pas de confirmation, idéal pour le streaming ou le jeu en ligne.
- Applications multimédia (audio et vidéo) en direct, VoIP, Vidéoconférence, Streaming
- Applications simples de demande et de réponse, DNS (peut aussi être sur TCP >512o), DHCP
- Applications qui gèrent elles mêmes la fiabilité, SNMP peut aussi être sur TCP), TFTP
(Full) Duplex : envoyer et recevoir, communication à deux sens
En Full-duplex, on peut envoyer et recevoir des données simultanément (comme au téléphone).

Semi-duplex : envoyer ou recevoir, communication à un sens
En Semi-duplex (Half), on ne peut faire qu'un seul à la fois (comme avec un Talkie-walkie).

CIDR: Classless Inter-Domain Routing
Méthode d'adressage IP qui remplace les anciennes classes (A, B, C) par une notation avec slash (ex: /24). Elle permet une gestion beaucoup plus souple et précise des masques de sous-réseau.

FTP: File transfert protocol
FTP transfère des fichiers en clair 

SFTP
SFTP sécurise le transfert via SSH

TFTP
Le TFTP est une version très simplifiée utilisée pour le démarrage réseau (PXE) ou la mise à jour d'équipements.

IP : Internet Protocol
Protocole de la couche 3 (Réseau) chargé de l'adressage et du routage des paquets de données. C'est lui qui permet à deux machines de se localiser sur un réseau, qu'il soit local ou mondial.

IPv4
Version standard codée sur 32 bits (4 octets), offrant environ 4 milliards d'adresses. À cause de la pénurie d'adresses, elle utilise souvent le NAT pour permettre à plusieurs machines de partager une seule IP publique.

IPv6
Successeur de l'IPv4 codé sur 128 bits, offrant un nombre d'adresses quasi illimité. Il simplifie l'en-tête des paquets et intègre nativement des fonctions de sécurité et d'auto-configuration.

Adresse IP : adresse internet protocol
- Ipv4 : adresse 32bits, 4 octets (4x8=32bits)
- Ipv6 : adresse 128bits 8 x 2octets ( 4x hexadécimal) (8x2x8=128bits)
#### IPv4
Plages d’adresses ipv4 : Pour /24 256 adresses - adresse réseau - adresse broadcast (diffusion) : 254 adresses utilisables
Longueur du préfixe réseau ipv4 : nombres de bits à 1 dans le masque sous réseau, CIDR /24 par exemple
Masque de sous réseau ipv4 :
- 255.0.0.0 : /8
- 255.255.0.0 : /16
- 255.255.255.0 : /24
- 255.255.255.128 : /25
- 255.255.255.192 : /26
- 255.255.255.224 : /27
- 255.255.255.240 : /28
- 255.255.255.248 : /29
- 255.255.255.252 : /30
- 255.255.255.254 : /31
Binaire pour masque sous réseau ipv4 :
	- 11111111 : 255
	- 11111110 : 254
	- 11111100 : 252
	- 11111000 : 248
	- 11110000 : 240
	- 11100000 : 224
	- 11000000 : 192
	- 10000000 : 128
Mono-diffusion : à destination d’un seul hôte
Diffusion : à destination de tous les autres hôtes
- Adresse 255.255.255.255 ou adresse réseau de broadcast (ex: 192.168.1.255)
Multi-diffusion : à destination d’une selection de plusieurs ou un hôte
- Adresses ipv4 de 224.0.0.0 à 239.255.255.255
Anciennes classes adresses ipv4 :
- La classe A de l’adresse IP 0.0.0.0/8 à 127.255.255.255/8 (privées et publiques).
- La classe B de l’adresse IP 128.0.0.0/16 à 191.255.255.255/16 (privées et publiques).
- La classe C de l’adresse IP 192.0.0.0 à 223.255.255.255/24 (privées et publiques).
- Adresses privées, RFC 1918 :
	- Les adresses IP privées de la classe A (/8) : 10.0.0.0 à 10.255.255.255
	- Les adresses IP privées de la classe B (/12) : 172.16.0.0 à 172.31.255.255
	- Les adresses IP privées de la classe C (/16) : 192.168.0.0 à 192.168.255.255
- Adresses ipv4 de bouclage : 127.0.0.0 ou 127.0.0.1 à 127.255.255.254
- Adresses link-local ou APIPA (automatic Private IP Addressing) : 169.254.0.0 ou 169.254.0.1 à 169.254.255.254, utilisé par un client DHCP windows si aucun serveur DHCP n’est disponible
#### IPv6
Adresses ipv6 GUA : Global Unicast Address, adresses de diffusion globale, structure :
- Préfixe de routage global (ex: 48bits si /64)
- ID de sous réseau (ex: 16bits si /64)
- ID d’interface (ex: 64bits si /64)
Adresses ipv6 LLA : Link Local Address, adresses de diffusion locale
- Commence par FE80 à FEBF (monodiffusion link-local)
Adresses ipv6 ULA : Link Local Unique
- Commence par FC00 à FDFF
Adresses ipv6 multidiffusion, commence par le préfixe FF00::/8
- Adresses multidiffusion attribuées :
	- Groupe de multidiffusion à tous les noeuds, FF02::1
	- Groupe de multidiffusion à tous les routeurs, FF02::2
- Adresses multidiffusion de noeud sollicité
Adresses ipv6 anycast : monodiffusion aléatoire
IPv6 ND: Neighbor Discovery protocol
Remplace ARP en IPv6. Il permet aux machines d'un même lien de découvrir les routeurs, les voisins et de vérifier si une adresse IP est déjà utilisée.
SLAAC : Stateless Address Autoconfiguration
Méthode permettant à un appareil de s'attribuer automatiquement une adresse IPv6 sans serveur DHCP, en utilisant les annonces du routeur (RA).
EUI : EUI 64-bits code composé d’une partie de l’adresse Mac, identifiant unique (OUI 24bits) avec 7ème bit inversé (en partant de la gauche) et de l’id de périphérique (24bits), avec au milieu 16 bits FFFE
ICMPv4 :
- Dépassement de délai : message de dépassement de délai à l’hôte source (champ utilisé : TTL)
- Codes de destination inaccessible :
	- 0 Réseau inaccessible
	- 1 Hôte inaccessible
	- 2 Protocole inaccessible
	- 3 Port inaccessible
ICMPv6 :
- RS : Message de sollicitation de routeur
- RA : Message d’annonce de routeur (toutes les 200sec et en réponse au RS)
- NS : Message de sollicitation de voisin (pour la DAD, Détection d’adresse en double)
- NA : Message d’annonce de voisin (pour connaître l’adresse MAC de destination)
- Dépassement de délai : message de dépassement de délai à l’hôte source (champ utilisé : Hop Limit IPv6)
- Codes de destination inaccessible :
	- 0 Pas de route vers la destination
	- 1 Communication interdite vers la destination
	- 2 Au-delà de la portée de l’adresse source
	- 3 Adresse inaccessible
	- 4 Port inaccessible
Protocole NDP : Neighbor Discovery Protocol (ND)
DHCPv6 : messages SOLICIT, ADVERTISE, INFORMATION, REQUEST, REPLY

PDU : unités de données de protocole. La PDU est l'unité de donnée à chaque couche (Trame, Paquet, Segment)
MTU : unité de transmission maximale. La MTU est la taille max d'un paquet (souvent 1500 octets)
TTL : Durée de vie. Le TTL est le compteur qui évite qu'un paquet ne tourne en boucle infinie

DHCP
DHCP (Dynamic Host Configuration Protocol) : Service qui attribue automatiquement une configuration réseau (IP, masque, passerelle, DNS) aux machines du parc. Il évite les erreurs de saisie manuelle et les conflits d'adresses IP. Processus de fonctionnement : DORA.
1. Discover : Le client envoie un message en "Broadcast" (tout le monde l'entend) pour chercher un serveur DHCP.
2. Offer : Le serveur répond en proposant une adresse IP disponible.
3. Request : Le client accepte la proposition et demande officiellement à utiliser cette adresse.
4. Acknowledge (ACK) : Le serveur valide et envoie les options (Masque, Passerelle, DNS).

DNS
DNS (Domain Name System) : Annuaire de l'Internet qui traduit les noms de domaines (ex: google.fr) en adresses IP techniques. Sans lui, les utilisateurs devraient retenir des suites de chiffres pour chaque site ou serveur.

Type d'enregistrement DNS (Utilité/Rôle)
Enregistrements courants :
- A (Address) Record Associe un nom de domaine (ou un nom d'hôte) à une adresse IPv4.
- AAAA (IPv6 Address) Record Associe un nom de domaine (ou un nom d'hôte) à une adresse IPv6.
- CNAME (Canonical Name) Record Fournit un alias pour un nom de domaine ou nom d'hôte (comme un pseudo)
- MX (Mail Exchange) Record Indique les serveurs de messagerie pour le domaine.
- PTR (Pointer) Record Utilisé dans les zones inversées pour résoudre les adresses IP en noms de domaine.
- NS (Name Server) Record Indique les serveurs de noms autoritaires pour le domaine (ou la zone).
- SOA (Start of Authority) Record Fournit des informations d'autorité pour une zone DNS.
- SRV (Service) Record Utilisé pour spécifier des services disponibles sur un domaine.
- TXT (Text) Record Stocke des données textuelles pour des informations diverses.
- Enregistrements moins courants ou spécialisés
- NAPTR (Naming Authority Pointer) Record Fournit des informations sur la manière de traduire un nom de domaine.
- HINFO (Host Information) Record Contient des informations sur le type de matériel et de système d'exploitation.
- LOC (Location) Record Fournit des informations de localisation géographique.
- SSHFP (SSH Fingerprint) Record Stocke les empreintes digitales des clés SSH.
- TLSA (TLS Authentication) Record Spécifie des informations d'authentification pour les certificats TLS/SSL.
- CAA (Certification Authority Authorization) Record Spécifie quelles autorités de certification sont autorisées à émettre des certificats.
- DNSKEY (DNS Key Record) Stocke des clés publiques de sécurité DNS.
- DS (Delegation Signer) Record Crée une chaîne de confiance pour les clés DNSSEC.
- WKS (Well-Known Services) Record Associe des services bien connus à un nom de domaine.
- RP (Responsible Person) Record Fournit des informations sur la personne responsable du domaine.
- DNAME (Delegation Name) Record Crée des alias de domaine.
Routage statique
Configuration manuelle des routes dans la table de routage d'un équipement. C'est une méthode simple et sécurisée, mais difficile à maintenir dès que le réseau devient complexe.

Routage dynamique
Utilisation de protocoles (ex: OSPF, RIP, BGP) pour que les routeurs échangent automatiquement leurs informations. Le réseau s'adapte alors tout seul en cas de coupure d'un lien ou de modification de la topologie.

Protocoles de routage dynamique :
- IGP: Interior gateway protocol :
	- RIP: Routing information protocol (limité à 15 sauts, un peu lent)
	- EIGRP: Enhanced Interior Gateway Routing Protocol (propriétaire Cisco, hybride)
	- OSPF: Open shortest path first (pour grand réseau, complexe mais performant)
- EGP: Exterior gatway protocol :
	- BGP: border gateway protocol (pour réseau externe/étendu)
Protocole SNMP : Simple Network Management Protocol
Protocole de gestion et de surveillance. Il permet à un serveur de supervision (ex: Zabbix) de collecter des statistiques (CPU, trafic) sur les équipements réseau.

NTP : Network Time Protocol, basé sur UDP, port 123. Protocole qui permet de synchroniser via le réseau l’horloge des appareils, d’ordinateurs etc. Service de synchronisation temporelle (Port UDP 123). Crucial pour la cohérence des logs, les certificats SSL et le fonctionnement d'Active Directory

Codecs : co(deur), déc(odeurs)s
- Taux d’échantillonnage : nombre d’échantillons /s
- Débit binaire ou bitrate : debit d’échantillons /s
- Différence entre taille d’origine et final

Wi-Fi: Wireless Fidelity (802.11)
Ensemble de protocoles de communication sans fil pour réseaux locaux (WLAN).

Adresse MAC : adresse ethernet 48 bits, constitué de deux parties l’OUI, identifiant unique d’entité (24bits) et l’ID de périphérique (24bits)
SSID : Nom d'identification d'un réseau Wi-Fi. C'est ce que l'utilisateur voit lorsqu'il cherche un réseau pour se connecter.
WEP: Wired equivalent privacy
Ancien protocole de sécurité Wi-Fi, aujourd'hui totalement obsolète car très facile à pirater.
WPA/WPA2/WPA3: Wi-Fi Protected access
Protocoles de sécurisation Wi-Fi successifs. Le WPA3 est le plus récent et le plus robuste contre les attaques par force brute.

TKIP: Temporal Key Integrity Protocol
AES: Advanced Encryption Standard
Protocoles de chiffrement. Le TKIP est ancien et lié au WPA, tandis que l'AES est la norme moderne, ultra-sécurisée, utilisée par le WPA2 et WPA3.

IEEE 802.11 : Normes pour réseau local sans fil WLAN
Norme de communication sans fil pour les réseaux locaux

IEEE 802.3 : Normes pour réseau Ethernet
Norme de câblage et de communication dominante pour les réseaux locaux filaires.

IEEE 802.15 : Normes pour WPAN, Bluetooth, RFID, …
Normes dédiées aux réseaux personnels sans fil (WPAN), incluant le Bluetooth et le Zigbee.

Protocole ARP : Address Resolution Protocol, pour déterminer l’adresse MAC de destination
Protocole qui fait le lien entre une adresse IP (logique) et une adresse MAC (physique) sur un réseau local IPv4.

Méthode CSMA/CA: Carrier Sense Multiple Access/Collision Avoidance
Méthode d'accès utilisée en Wi-Fi pour éviter les collisions : l'appareil écoute si le canal est libre avant de transmettre.

NIC : carte réseau classique
HBA : Hot bus adapter, carte réseau spécifique pour connecter un serveur à un réseau de stockage (SAN)

Protocole ICMP : Internet Control Message Protocol
Adresse MAC: Adresse physique (Media access control)
Port trunk
AS: Autonomous system
DHCP: Dynamic Host Configuration Protocol, adressage dynamique
PPP: Point to point protocol
Internet: réseau de réseaux
LLC: sous couche Logical Link Control (viabilise le protocole MAC)
MAC: sous couche Médium Access Control

NAT: Network Adress Transmission

PAN: reseau personnel (ex : bluetooth)
LAN: Local Area network, réseau local (ex: bureau)
MAN: réseau métropolitain (ex : ville)
WAN: réseau étendu (ex : pays/Internet)
WLAN: réseau local sans fil
VLAN: réseau local virtuel
Découpage logique du réseau en plusieurs réseaux isolés pour améliorer la sécurité et réduire le trafic de diffusion.

Protocoles de contrôle : CDP, VTP, PAgP et DTP

TFTP : Trivial file transfer protocol. Version très simplifiée de FTP, sans authentification, utilisée pour transférer des fichiers légers (configurations, boot PXE).
HTTP : Hypertext transfer protocol. Protocole de transfert web
HTTPS : HTTP security, chiffrement SSL/TLS. Protocole de transfert web HTTP qui ajoute une couche de chiffrement SSL/TLS pour garantir la confidentialité et l'intégrité

REST : Style d'architecture pour les services web (APIs) permettant aux applications de communiquer simplement via HTTP.
DNS : domain name system
DNSSEC : DNS security extensions. Sécurise les réponses DNS
DDNS : DNS dynamique. DDNS met à jour l'IP d'un nom dynamiquement
rDNS/DNS inversé : permet de trouver le nom à partir de l'IP

URI : uniform resource identifier. Identifiant global
URL : uniform resource locator, sous la forme : préfixe.domainedns.extension(tld)

TLD : Top level domain, extension d’une url

LDAP : Lightweight Directory Access Protocol
Protocole permettant d'interroger et de modifier des services d'annuaire (comme Active Directory) pour l'authentification des utilisateurs.

Mesures de performance :
- Latence : Temps de retard dans la transmission d'une donnée (le "ping").
- Bande passante : La bande passante est le débit théorique maximum
- Taux de rendement / Troughput : le débit réel mesuré
- Disponibilité
- Capacité de montée en charge / Scalability : Capacité d'un système à s'adapter à une augmentation de la charge (nombre d'utilisateurs ou de données).
- Redondance et tolérance aux pannes : Multiplication des composants critiques pour éviter qu'une seule panne ne paralyse tout le système.
- Tests de charge


#### Messagerie
SMTP : Simple Mail Transfert Protocol, envoi des mails (port 25)
POP3 : Post Office Protocol, téléchargement des mais (port 110)
IMAP : Internet Message Access Protocol, consultation, manipulation des mails (port 143
### Réseau, matériel physique

AP : point d’accès (wifi)
Box (internet)
Routeur
Switch : Commutateur
Serveur
Baie de stockage
NAS
RJ11 : Connecteur, norme RJ11 (registered jack) à 6 broches utilisé pour des appareils téléphoniques fixes
RJ45 : Connecteur, norme RJ45 à 8 broches utilisé pour les connexions ethernet (protocole de communication) dans les réseaux informatiques pour différents appareils et aussi pour les appareils téléphoniques
Équipements numérique : Ordinateur, tablette, smartphone, objet connecté (tv, montre, …)
PoE : Power over ethernet, alimentation via câble ethernet
PoE+ : Power over ethernet plus, prend en charge plus de puissance et données sur un seul câble
Carte mère : Interfaces E/S, Socket CPU, Chipset, BIOS, Ports PCI, Slot (SO)DIMM RAM, ports SATA, ports M.2
Chipset : 
- Northbridge : permet un accès rapide à la mémoire RAM et à la carte graphique.
- Southbridge : permet au processeur de communiquer avec des périphériques plus lents, comme des disques durs, des ports USB ou des slots d’extension.
CPU : Central Processing Unit, puce électronique qui interprète et exécute des commandes. Il est dans un emplacement identifié appelé « socket ». Il existe deux connexions possibles en fonction du processeur, entre le CPU et le socket, le PGA (Pin Grid Array, ou matrice de broches) ou le LGA (Land Grid Array ou matrice de pastilles).
GPU : Graphic Processing Unit, puce électronique 
ROM : Read Only Memory, Mémoire BIOS/UEFI
RAM : Random Access Memory, Mémoire vive (de travail)
USB : Universal Serial Bus
M.2 : connectique compatible SATA, PCie, NVMe
SoC : System on chip, puce de circuits électroniques qui intègre le processeur, le processeur graphique, la mémoire vive, le sans-fil et d’autres composants essentiels
Cluster computing : empilement d’ordinateurs
GPU Accelerated Computing : utilisation de cartes graphiques haute performance pour accélérer les calculs dans les superordinateurs.
### Virtualisation
Virtualisation :
KVM
LXC
VM : Machine virtuelle
Hyperviseur
Hyperviseur de type 1
Hyperviseur de type 2
Hyperviseur de type 2 :
- Virtualbox (Windows/macOS/Linux)
- VMware workstation (Windows/Linux)
- VMWare fusion (macOS)
- Parallels desktop (macOS)
- UTM (macOS)
Hyperviseur de type 1 :
- Proxmox (Linux KVM)
- VMware vSphere
- Hyper-V server
- Citrix hypervisor
Hyper-V :
- Switch (Commutateur) virtuel
- Switch privé
- Switch interne
- Switch externe
ESXi vCenter :
- Esxi
- vSphere Standard Switch (vSS)
- vCenter
- vSphere
- vmNIC est l'objet vSphere associé à une pNIC
- pNIC est la carte physique de l'hôte
- VM Kernel
- vMotion
- VMFS : Virtual Machine File System
- DRS : Distributed resource scheduler
- vSphere HA
- EVC
- VSAN
Proxmox :
- HA Manager
- Ceph storage

### Surveillance système et réseau, Supervision

Supervision :

Syslog : est un protocole définissant un service de journaux d'événements d'un système informatique. C'est aussi le nom du format qui permet ces échanges.

Logs : fichiers de journalisation, journaux d'évènements
 
### Sécurité
Protection des accès à Internet :
- Pare-feux / Firewall
- Systèmes de détection d’intrusion / IDS
- Systèmes de prévention d’intrusion / IPS
- Proxy
- Filtrage de contenu
- Réseaux privé virtuels / VPN
- Systèmes de prévention des pertes de données / DLP (Data loss prevention)
- Filtrage mail
- Gestionnaire d’authentification à deux facteurs / 2FA
- Solutions anti-DDos
- Filtrage DNS
Chiffrement
Clé publique
Clé secrète
Certificat
Pare-feu : Filtrage IP
Proxy
Anti-virus
Anti-spam
Anti-malware
DMZ : zone démilitarisé, adresses ip publiques dans un réseau privée
VPN
VPN site à site
SSH
Phishing
Spam
Sim swap
Vishing
Ransomware
Malware: logiciel malveillant
Spyware: logiciel espion
Virus
VPN: réseau privé virtuel
ACL: listes de contrôle d’accès
PKI : Public key infrastructure
Chiffrement asymétrique: public key et private key
CA : Certificate Authority, autorité de certification
Dos : attaque par déni de service (un hôte attaquant)
DDos : attaque par déni de service distribué (multiples hôtes attaquants
IDS : Intrusion Detection system. Systèmes de détection des intrusions (Snort, Suricata…)
IPS : Intrusion Prevention system. Systèmes de prévention des intrusions. (Cisco Firepower, Palo Alto networks…)
SIEM : Gestion de l’information et des événements de sécurité, combinaison de SIM et SEM (Graylog, Fusion SIEM)
Security Information and Event Management, systèmes de gestion des événements et des informations de sécurité
Détections :
- Détection basée sur des signatures
- Détection basée sur le comportement
- Détection d’anomalis
- Détection d’attaques réseau
IoC : Indicateurs de compromission
Tests de sécurité :
- Tests de pénétration / pentests : Test avec simulation d’attaques
- Tests d’intrusion : Test avec simulation d’intrusion, notamment des IDS et IPS
- Tests de vulnérabilité : test des vulnérabilité connues CVE
- Tests de performance : test la haute disponibilité des services en cas de charge élevée
Logiciels de sécurité courants :
- Whireshark
- Nmap
- OpenVAS (GVM)
- Nessus
- BurpSuite
- Metasploit
- Snort

### Serveurs et OS

Shell :

SMB : Server Message Block, serveur de partage de fichier (Samba), multi-environnement
### Windows et Windows Server

Active Directory
LDAP : Lightweight Directory Access Protocol
GPO: Group policy object, stratégie de groupe
WDS
ADDS : active directory domain service 
MDT : microsoft deployment toolkit
WSUS : windows server update services, serveur de récupération de mise à jour
SCVMM : System center virtual machine manager (microsoft)
PowerShell
CMD

### Unix/Linux

NFS : Network File System, serveur de partage de fichier Unix/Linux
Bash

### Sauvergarde et restauration

Sauvegarde on-line, near-line, off-line

Sauvegarde totale, incrémentielle, différentielle

Masters : Images

### Téléphonie

#### ToIP, Téléphonie IP
Téléphonie sur IP (« ToIP » pour Telephony over Internet Protocol), qui concerne les fonctions réalisées par un autocommutateur téléphonique IPBX.
#### VoIP 
La voix sur IP[1], ou « VoIP » pour « Voice over Internet Protocol », est une technique informatique qui permet de transmettre la voix sur des réseaux compatibles IP, via Internet ou des réseaux privés ( intranets) ou publics, qu'ils soient filaires ( câble/ ADSL/ fibre optique) ou non ( satellite, Wi-Fi et réseaux mobiles).
#### IPBX
Internet Protocol Private Branch eXchange, autocommutateur téléphonique privé physique ou logiciel, serveur ou cloud.
#### Centrex
IPBX dans le cloud (stocké dans un data center)

Exemples de solution de téléphonie IP
- FreePBX
- Xivo

#### Softphone
Téléphone IP logiciel sur ordinateur, tablette, smartphone etc
#### CTI
couplage téléphonie-informatique

#### QoS, Quality of service

#### RSVP

#### Proxy SIP

#### Trunk SIP

#### LUN

Passerelle/adaptateur téléphonique analogique
pour un réseau hybride, assure la compatibilité entre réseau analogique et réseau numérique en convertissant les signaux analogiques en donnes numériques
Téléphone IP : Deux ports ethernet, un pour le réseau et un pour la connexion à un PC
SVI : Serveur Vocal Interactif
Codecs :
- G.711 : 64Kbps non compressé, haute qualité mais grosse bande passante
- G.729 : 8Kbps compressé qualité moyenne/basse mais léger
VoIP : Téléphonie IP, Voice over Internet Protocol
SIP : Session Initiation Protocol, chargé de l’initialisation, le maintien et la fermeture de la communication
SCCP : Skinny Call Control Protocol (propriétaire Cisco)
SDP : Session Description Protocol, chargé de la communication des paramètres
RTP : Real-time Transfert Protocol, chargé de l’acheminement des données
RTCP : Real-time Transport Control Protocol, chargé de l’acheminement du contrôle qualité
SRTP : Secure Real-Time Transfert Protocol, chargé de la sécurisation de la communication
DTLS : Datagram Transport Layer Security, chargé de la sécurisation de la communication
Réseau RTC
PABX
ISDN
RNIS (Numéris)
SDA : sélection directe à l’arrivée
T0/T2

Protocoles : 
LDAPS : 636 TCP/UDP
RTP : 5004-5005 UDP
SIPS : 5061 TCP/UDP
NFS : 2049 TCP


Normes 802 : 
			Norme
			Nom commun
			Ce qu'il faut retenir
			802.3
			Ethernet
			La norme pour les réseaux filaires (cuivre ou fibre).
			802.11
			Wi-Fi
			La norme pour les réseaux sans-fil (WLAN). Déclinée en a/b/g/n/ac/ax.
			802.1Q
			VLAN Tagging
			La norme qui permet de faire circuler plusieurs VLANs sur un lien Trunk.
			802.1X
			Authentification
			Sécurise l'accès au réseau (port-based). L'utilisateur doit s'authentifier (souvent via un serveur RADIUS) avant que le switch n'ouvre le port.