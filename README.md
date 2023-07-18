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

