```html
<h1 align="center">🔐 MITM Attack Simulation Using ARP Spoofing</h1>

<p align="center">
  <strong>Kali Linux | Ettercap | Bettercap | Oracle VirtualBox</strong>
</p>

<hr>

<h2>📌 Description du projet</h2>

<p>
  Ce projet consiste à simuler une attaque
  <strong>Man-in-the-Middle (MITM)</strong> basée sur
  l'<strong>ARP Spoofing</strong> dans un environnement réseau contrôlé,
  en utilisant Kali Linux, Ettercap et Bettercap.
</p>

<p>
  L'objectif est de comprendre les vulnérabilités du protocole ARP,
  d'étudier les risques d'interception des communications réseau
  et d'explorer les mécanismes de protection contre ces attaques.
</p>

<h2>🎯 Objectifs</h2>

<ul>
  <li>Comprendre le fonctionnement du protocole ARP.</li>
  <li>Étudier le principe d'une attaque MITM.</li>
  <li>Découvrir les techniques d'ARP Spoofing.</li>
  <li>Identifier les équipements connectés au réseau local.</li>
  <li>Utiliser Ettercap et Bettercap pour l'analyse réseau.</li>
  <li>Observer les communications et les paquets réseau.</li>
  <li>Étudier les mécanismes de détection et de prévention.</li>
</ul>

<h2>🛠️ Outils et technologies utilisés</h2>

<table>
  <tr>
    <th>Outil</th>
    <th>Utilisation</th>
  </tr>
  <tr>
    <td>Kali Linux</td>
    <td>Système d'exploitation dédié aux tests de sécurité.</td>
  </tr>
  <tr>
    <td>Ettercap</td>
    <td>Découverte des hôtes et analyse des communications réseau.</td>
  </tr>
  <tr>
    <td>Bettercap</td>
    <td>Reconnaissance réseau, étude de l'ARP Spoofing et capture de trafic.</td>
  </tr>
  <tr>
    <td>Oracle VirtualBox</td>
    <td>Virtualisation de la machine Kali Linux.</td>
  </tr>
  <tr>
    <td>ARP</td>
    <td>Résolution des adresses IPv4 en adresses MAC.</td>
  </tr>
  <tr>
    <td>TCP/IP</td>
    <td>Communication entre les équipements réseau.</td>
  </tr>
  <tr>
    <td>mDNS</td>
    <td>Protocole de découverte et de résolution de noms locaux.</td>
  </tr>
</table>

<h2>🖥️ Environnement de simulation</h2>

<table>
  <tr>
    <th>Équipement</th>
    <th>Adresse IP</th>
  </tr>
  <tr>
    <td>Machine Kali Linux</td>
    <td>192.168.100.13</td>
  </tr>
  <tr>
    <td>Passerelle réseau</td>
    <td>192.168.100.1</td>
  </tr>
  <tr>
    <td>Réseau local</td>
    <td>192.168.100.0/24</td>
  </tr>
  <tr>
    <td>Hôte découvert 1</td>
    <td>192.168.100.4</td>
  </tr>
  <tr>
    <td>Hôte découvert 2</td>
    <td>192.168.100.5</td>
  </tr>
  <tr>
    <td>Hôte découvert 3</td>
    <td>192.168.100.8</td>
  </tr>
</table>

<h2>🧠 Principe de l'attaque MITM</h2>

<p>
  Une attaque Man-in-the-Middle consiste à interposer une machine
  entre deux équipements qui communiquent.
</p>

<p>
  Dans le cas de l'ARP Spoofing, de fausses informations ARP
  peuvent provoquer une association incorrecte entre
  une adresse IP et une adresse MAC.
</p>

<p>
  Cette manipulation peut permettre la redirection du trafic
  réseau vers une machine intermédiaire.
</p>

<h3>Communication normale</h3>

<pre>
[Client] ---------> [Routeur] ---------> [Internet]
</pre>

<h3>Scénario MITM</h3>

<pre>
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
</pre>

<h2>🔬 Étapes de la simulation</h2>

<h3>1. Préparation de l'environnement</h3>
<p>
  Installation et configuration de Kali Linux dans Oracle VirtualBox,
  puis vérification de la connectivité réseau.
</p>

<h3>2. Découverte des équipements</h3>
<p>
  Utilisation de Bettercap et Ettercap pour identifier les équipements
  présents sur le réseau local ainsi que leurs adresses IP et MAC.
</p>

<h3>3. Étude de l'ARP Spoofing</h3>
<p>
  Exploration du module arp.spoof de Bettercap et de ses paramètres,
  notamment le fonctionnement du mode full-duplex.
</p>

<h3>4. Simulation MITM</h3>
<p>
  Démarrage du module ARP Spoofing dans l'environnement de test.
  Bettercap a signalé le lancement du module ainsi qu'un avertissement
  concernant les protections ARP du routeur.
</p>

<h3>5. Observation du trafic</h3>
<p>
  Utilisation de net.sniff pour observer les paquets réseau visibles
  depuis la machine Kali Linux, notamment des requêtes mDNS.
</p>

<h3>6. Analyse avec Ettercap</h3>
<p>
  Exploration de l'interface graphique d'Ettercap et consultation
  de la liste des hôtes découverts.
</p>

<h2>📊 Résultats et observations</h2>

<ul>
  <li>Découverte de plusieurs équipements du réseau local.</li>
  <li>Identification des adresses IP et MAC.</li>
  <li>Exploration des fonctionnalités ARP Spoofing.</li>
  <li>Démarrage du module arp.spoof dans Bettercap.</li>
  <li>Observation d'un avertissement relatif aux protections ARP.</li>
  <li>Détection de requêtes mDNS dans les journaux.</li>
  <li>Visualisation des équipements dans Ettercap.</li>
</ul>

<p>
  <strong>Remarque :</strong>
  Les captures disponibles ne suffisent pas à confirmer
  la réussite d'une interception MITM complète.
</p>

<h2>🛡️ Mesures de protection</h2>

<ul>
  <li>Dynamic ARP Inspection (DAI).</li>
  <li>DHCP Snooping.</li>
  <li>Surveillance des changements d'associations IP/MAC.</li>
  <li>Utilisation de HTTPS et TLS.</li>
  <li>Segmentation du réseau local.</li>
  <li>Activation des protections ARP du routeur.</li>
</ul>

<h2>📚 Compétences développées</h2>

<ul>
  <li>Cybersécurité et sécurité des réseaux.</li>
  <li>Compréhension des protocoles ARP et TCP/IP.</li>
  <li>Administration de Kali Linux.</li>
  <li>Virtualisation avec Oracle VirtualBox.</li>
  <li>Reconnaissance et analyse réseau.</li>
  <li>Étude des attaques MITM.</li>
  <li>Analyse des mécanismes de défense.</li>
</ul>


<h2>📌 Conclusion</h2>

<p>
  Ce projet a permis d'explorer les principes des attaques
  Man-in-the-Middle et de l'ARP Spoofing en utilisant
  Kali Linux, Ettercap et Bettercap.
</p>

<p>
  Il met en évidence l'importance des mécanismes de protection
  du réseau local et constitue une introduction pratique
  à l'analyse des vulnérabilités réseau.
</p>

<hr>

<p align="center">
  <strong>
    Kali Linux • Ettercap • Bettercap • VirtualBox •
    ARP Spoofing • MITM • Network Security
  </strong>
</p>
```
