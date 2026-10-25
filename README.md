🔐 MITM Attack Simulation Using ARP Spoofing — Kali Linux

📌 Description du projet

Ce projet consiste à étudier et simuler une attaque Man-in-the-Middle (MITM) basée sur la technique d'ARP Spoofing (ARP Poisoning) dans un environnement réseau contrôlé, à l'aide de Kali Linux, Ettercap et Bettercap.

L'objectif est de comprendre les vulnérabilités du protocole ARP (Address Resolution Protocol), d'observer le comportement des équipements d'un réseau local et d'analyser les risques liés à l'interception des communications.

Cette simulation s'inscrit dans une démarche pédagogique de cybersécurité et de sécurité des réseaux informatiques.

🎯 Objectifs du projet

Comprendre le fonctionnement du protocole ARP.

Étudier le principe d'une attaque Man-in-the-Middle (MITM).

Découvrir les techniques d'ARP Spoofing.

Identifier les équipements connectés à un réseau local.

Expérimenter les fonctionnalités d'Ettercap et de Bettercap.

Observer et analyser les communications réseau.

Identifier les mécanismes de protection contre l'ARP Spoofing.

Comprendre les méthodes de détection et de prévention des attaques MITM.

🛠️ Outils et technologies utilisés

Outil / Technologie

Description

Kali Linux

Distribution Linux spécialisée dans les tests de sécurité et l'analyse réseau.

Ettercap

Outil d'analyse réseau et de simulation d'attaques Man-in-the-Middle.

Bettercap

Framework de sécurité réseau permettant la découverte des hôtes, l'analyse du trafic et les tests ARP.

Oracle VirtualBox

Logiciel de virtualisation utilisé pour exécuter Kali Linux.

ARP

Protocole permettant d'associer une adresse IPv4 à une adresse MAC sur un réseau local.

TCP/IP

Ensemble de protocoles assurant la communication entre les équipements du réseau.

mDNS

Protocole de résolution de noms sur un réseau local, observé durant la capture.

🖥️ Environnement de simulation

La simulation a été réalisée à partir d'une machine virtuelle Kali Linux exécutée sous Oracle VirtualBox.

Configuration réseau observée

Élément

Adresse IP

Machine Kali Linux

192.168.100.13

Passerelle réseau

192.168.100.1

Réseau local

192.168.100.0/24

Hôte découvert

192.168.100.4

Hôte découvert

192.168.100.5

Hôte découvert

192.168.100.8

Les adresses correspondent à l'environnement de simulation présenté dans les captures d'écran.

🧠 Principe de l'attaque MITM

Une attaque Man-in-the-Middle consiste à placer un équipement intermédiaire entre deux systèmes qui communiquent.

Dans le cas de l'ARP Spoofing, l'attaquant cherche à envoyer de fausses informations ARP afin d'associer son adresse MAC à l'adresse IP d'un autre équipement, généralement la passerelle réseau.

Si cette manipulation réussit, une partie du trafic peut être redirigée vers la machine intermédiaire.

Schéma conceptuel

Communication normale :

[Client] ────────── [Routeur]
                         |
                     [Internet]


Scénario MITM :

[Client]
    |
    v
[Machine intermédiaire]
    |
    v
[Routeur]
    |
    v
[Internet]

Le succès de cette technique dépend notamment de la configuration du réseau et des mécanismes de protection actifs.

🔬 Déroulement de la simulation

1. Préparation de l'environnement

Installation et démarrage de Kali Linux dans Oracle VirtualBox.

Vérification de la connectivité réseau et identification de l'adresse IP de la machine virtuelle.

2. Découverte des équipements réseau

Utilisation des fonctionnalités de reconnaissance réseau de Bettercap et d'Ettercap pour identifier les équipements présents sur le sous-réseau.

Les opérations de découverte ont permis d'observer plusieurs adresses IP et MAC.

3. Étude de l'ARP Spoofing

Exploration du module arp.spoof de Bettercap afin de comprendre son fonctionnement et ses paramètres.

Les tests ont notamment porté sur le mode full-duplex, qui concerne les échanges entre la cible et la passerelle.

4. Simulation de l'attaque MITM

Démarrage du module d'ARP Spoofing dans l'environnement de test.

Bettercap a confirmé le démarrage du module, tout en affichant un avertissement relatif aux mécanismes de protection ARP du routeur.

Cette indication ne constitue pas une preuve que l'interception du trafic a réussi.

5. Observation du trafic réseau

Utilisation du module net.sniff de Bettercap pour observer les paquets visibles depuis la machine Kali Linux.

Les journaux ont notamment montré des requêtes mDNS.

Ces observations permettent d'étudier certains échanges locaux, mais ne démontrent pas à elles seules l'interception des communications d'un autre appareil.

6. Analyse avec Ettercap

Utilisation de l'interface graphique d'Ettercap pour explorer les équipements détectés et examiner leurs adresses IP et MAC.

Cette étape permet de compléter les observations effectuées avec Bettercap.

📊 Résultats et observations

Les captures d'écran de la simulation montrent les résultats suivants :

Détection de plusieurs équipements sur le réseau local.

Identification de certaines adresses MAC et de leurs fabricants.

Exploration des fonctionnalités ARP Spoofing de Bettercap.

Démarrage du module arp.spoof.

Affichage d'un avertissement concernant les protections ARP.

Observation de requêtes mDNS.

Affichage de la liste des hôtes détectés dans Ettercap.

Limite de l'expérience : les captures disponibles ne permettent pas de confirmer qu'une attaque MITM complète a réussi ou que le trafic d'une cible a effectivement été intercepté.

🛡️ Mesures de protection

Plusieurs mécanismes peuvent contribuer à limiter les attaques ARP Spoofing :

Dynamic ARP Inspection (DAI) : vérification des messages ARP sur les équipements réseau compatibles.

DHCP Snooping : contrôle des informations d'attribution des adresses IP.

Surveillance ARP : détection des changements suspects d'association IP/MAC.

HTTPS et TLS : protection de la confidentialité et de l'intégrité des communications applicatives.

Segmentation réseau : limitation des communications directes entre équipements.

Sécurisation du routeur : activation des protections réseau disponibles.

📚 Compétences développées

Ce projet permet de renforcer plusieurs compétences techniques :

Sécurité des réseaux informatiques.

Analyse des protocoles TCP/IP et ARP.

Administration de Kali Linux.

Virtualisation avec Oracle VirtualBox.

Découverte et reconnaissance réseau.

Analyse du trafic réseau.

Compréhension des attaques MITM.

Étude des mécanismes de protection contre l'ARP Spoofing.

📌 Conclusion

Cette simulation a permis d'explorer les mécanismes de l'ARP Spoofing et le principe des attaques Man-in-the-Middle à travers les outils Ettercap et Bettercap sous Kali Linux.

L'expérience met en évidence l'importance de la surveillance du réseau local et des mécanismes de protection ARP.

Elle constitue une introduction pratique à l'analyse des vulnérabilités réseau et aux techniques de défense utilisées en cybersécurité.

Technologies : Kali Linux · Ettercap · Bettercap · VirtualBox · ARP · TCP/IP · Network Security

Domaine : Cybersécurité / Sécurité des réseaux / Ethical Hacking
