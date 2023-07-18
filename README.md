# ocd

# Introduction :

Ce rapport présente la conception et la mise en place d'un réseau d'entreprise dans le cadre de mon stage chez Orange Cyber Defense en utilisant le logicielt Packat Tracer. L'objectif principal de ce projet est de créer un réseau qui respecte les bonnes pratiques de sécurité et intègre les solutions de sécurité recommandées par des organismes tels que le NIST, Cisco et Fortinet. Le réseau est basé sur le modèle à trois couches de Cisco, offrant une architecture robuste et évolutive.
Ce modèle fournit une approche hiérarchique pour l'organisation du réseau. Cette approche facilite la gestion, la scalabilité et la résilience du réseau. Les trois couches comprennent la couche d'accès, la couche de distribution et la couche de cœur, chacune remplissant un rôle spécifique dans la connectivité et la sécurité du réseau.

# Conception du réseau :

## Définition des besoins :

Avant de commencer la conception du réseau, il est essentiel de comprendre les besoins spécifiques de l'entreprise. Cela comprend l'identification des différents départements, services et exigences en termes de connectivité, de sécurité et de performances.

## Modèle à trois couches de Cisco :

Le modèle à trois couches de Cisco est utilisé comme base pour la conception du réseau. Il se compose des couches suivantes :

- Couche d'accès : Cette couche est responsable de la connectivité des utilisateurs finaux et des périphériques au réseau.

- Couche de distribution : Elle assure la distribution du trafic entre les différentes parties du réseau.

- Couche de cœur : Cette couche gère le routage interne du réseau et assure la connectivité entre les différents sous-réseaux.

## Segmentation en sous-réseaux :

Pour assurer une meilleure gestion et une sécurité accrue, le réseau est segmenté en plusieurs sous-réseaux. Les départements tels que les ressources humaines (HR), la direction des systèmes d'information (DSI), la finance et les serveurs ont chacun leur propre sous-réseau.

## Redondance et disponibilité :

La redondance est un élément clé de la conception du réseau pour garantir la disponibilité des services. Des mesures de redondance sont mises en place au niveau des ISPs, des routeurs de cœur et des commutateurs multi-niveaux afin de permettre une continuité de service en cas de défaillance matérielle ou de panne.

# Configuration du reseaux :

a. ISPs (Fournisseurs d'accès Internet) :
Deux ISPs ont été mis en place pour assurer une redondance et une disponibilité maximale de la connectivité Internet. Cela permet également de répartir la charge du trafic.

b. Firewall :
Un pare-feu a été déployé entre les ISPs et la zone DMZ pour contrôler et filtrer le trafic entrant et sortant. Il est configuré pour appliquer des règles de sécurité strictes et effectuer des inspections approfondies des paquets pour prévenir les attaques.

c. Zone DMZ :
La zone DMZ contient les serveurs web, les serveurs de messagerie et les serveurs HTTP accessibles depuis Internet. Ces serveurs sont isolés du réseau interne par des pare-feu et sont configurés pour limiter les accès non autorisés.

d. Core Routeurs :
Deux routeurs de cœur ont été déployés pour assurer une connectivité redondante et gérer le routage interne du réseau. Ils sont configurés pour utiliser OSPF (Open Shortest Path First) pour un routage efficace et dynamique.

e. Multilayer Switches :
Deux commutateurs multi-niveaux sont utilisés pour la distribution du trafic à travers le réseau. Ils fournissent une connectivité aux différents sous-réseaux de l'entreprise et sont configurés pour assurer une segmentation appropriée et une isolation des différents services.

f. Subnets :
Quatre sous-réseaux ont été créés pour les différentes entités de l'entreprise : RH, DSI, Finance et Serveurs. Chaque sous-réseau est équipé de deux PC, un ordinateur portable, un point d'accès et des périphériques sans fil. Le sous-réseau Serveurs héberge également le serveur DHCP, le serveur DNS et le PC d'administration.

# Solutions de Sécurité:

a. Authentification et Gestion des Accès :
Tous les périphériques du réseau doivent être configurés avec des identifiants d'accès uniques et des mots de passe forts. Il est recommandé d'utiliser une politique de gestion des accès qui inclut des politiques de rotation régulières des mots de passe et des mécanismes d'authentification forte, tels que l'utilisation de certificats.

b. Contrôle d'Accès et Segmentation :
Utilisez des listes de contrôle d'accès (ACL) pour limiter les flux de trafic entre les différentes zones du réseau. Configurez les pare-feu pour autoriser uniquement les connexions nécessaires et restreindre le trafic non autorisé.

c. Surveillance et Détection d'Intrusion :
Mettez en place des outils de surveillance réseau et des systèmes de détection d'intrusion (IDS) pour détecter les activités suspectes ou les tentatives d'intrusion. Ces outils peuvent alerter les administrateurs en cas d'événements de sécurité et permettre une réponse rapide aux incidents.

d. Chiffrement et VPN :
Pour assurer la confidentialité des données sensibles, il est recommandé d'utiliser des connexions VPN (Virtual Private Network) pour les communications entre les différents sites de l'entreprise ou pour les accès à distance. Les données transitant via les VPN doivent être chiffrées pour empêcher toute interception ou compromission.

e. Mise à jour et Gestion des Correctifs :
Il est essentiel de maintenir tous les équipements réseau à jour avec les derniers correctifs de sécurité. Assurez-vous de mettre en place une politique de gestion des correctifs pour garantir que les vulnérabilités connues sont rapidement corrigées.

f. Formation en Sensibilisation à la Sécurité :
La sensibilisation à la sécurité est un élément crucial pour garantir la sécurité globale du réseau. Organisez régulièrement des sessions de formation et de sensibilisation à la sécurité pour tous les employés, afin de les informer des bonnes pratiques de sécurité, des risques potentiels et des mesures à prendre en cas d'incident.

Antivirus :
Les solutions antivirus sont essentielles pour détecter et éliminer les logiciels malveillants, les virus et les programmes indésirables. Elles doivent être déployées sur tous les systèmes, y compris les serveurs et les postes de travail, pour assurer une protection proactive contre les menaces.

XDR (Extended Detection and Response) :
Le XDR est une approche de sécurité étendue qui intègre la détection et la réponse des menaces sur plusieurs couches du réseau et des systèmes. Il collecte et analyse les données provenant de diverses sources, y compris les endpoints, les réseaux, les applications et les serveurs, afin de détecter les menaces avancées et d'y répondre rapidement.

EDR (Endpoint Detection and Response) :
L'EDR se concentre spécifiquement sur la détection et la réponse des menaces au niveau des endpoints (terminaux). Il surveille en temps réel les activités suspectes sur les endpoints, tels que les comportements malveillants, les tentatives d'intrusion et les activités de logiciels malveillants, et prend des mesures pour y remédier.

SIEM (Security Information and Event Management) :
Le SIEM est une solution de gestion des informations et des événements de sécurité qui collecte, corréle et analyse les journaux et les événements de sécurité à partir de diverses sources dans le réseau. Il permet aux équipes de sécurité de détecter les incidents, d'enquêter sur les menaces et de prendre des mesures appropriées en temps opportun.

Ces solutions de sécurité supplémentaires, telles que les antivirus, XDR, EDR et SIEM, sont souvent intégrées dans un cadre global de sécurité d'entreprise. Elles renforcent la détection, la protection et la réponse aux menaces sur le réseau et les systèmes de l'entreprise. En les ajoutant à votre réseau d'entreprise, vous améliorez la sécurité globale en surveillant et en protégeant activement contre les menaces connues et émergentes.
