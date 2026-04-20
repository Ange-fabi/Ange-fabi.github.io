# Fabienne Ange Jazet Tonleu

**Étudiante en Cybersécurité & Administration systèmes** – Recherche stage (juillet-septembre 2026) ou alternance (dès septembre 2026)

> *"J'attaque pour mieux défendre. Je documente pour mieux progresser."*

---

## 📌 À propos de moi

Actuellement en 1ère année du cycle ingénieur du numérique (bac+3) à l'ESAI d'Angers, je cherche un stage du 10 juillet au 10 septembre 2026 ou une alternance à partir de septembre 2026.

J'ai déjà réalisé deux stages :
- **Camaroes SARL** : audit de sécurité, tests de vulnérabilité
- **Africa Technology System** : développement d'une solution de suivi de flottes

En parallèle, je construis mon propre laboratoire technique à la maison (VMs Linux, Kali, Debian) pour maîtriser la sécurité offensive et défensive. Ce portfolio rassemble mes projets personnels.

📫 **Contact** : angejaz59@gmail.com | 07 53 42 33 98  
🔗 **GitHub** : [github.com/tonpseudo](https://github.com/tonpseudo)  
🔗 **LinkedIn** : [linkedin.com/in/tonpseudo](https://linkedin.com/in/tonpseudo)  
🌐 **CV** : [télécharger mon CV](./cv-fabienne-jazet.pdf)

---

## 🛠️ Compétences techniques

| Domaine | Technologies |
|---------|--------------|
| **🐧 Linux** | Debian, Ubuntu, administration serveur, SSH, systemd, nftables, Postfix |
| **🔐 Cybersécurité** | Hydra (brute force), Fail2ban, Nmap, détection d'intrusion, anti-spam |
| **🖧 Réseau** | TCP/IP, VLANs, ACLs, RIP, DNS, DHCP, SMTP, HTTP |
| **💻 Programmation** | C, C# (Unity), Bash, Git |
| **🧪 Virtualisation** | VirtualBox, Kali Linux, laboratoire isolé |

---

## 📁 Projets

### 1. 🔐 Brute force Hydra + contre-attaque Fail2ban
*Attaque et défense sur serveur web Apache*

**Objectif** : Simuler une attaque par dictionnaire, puis mettre en place une défense automatique.

**Actions réalisées** :
- Création d'un dictionnaire de 10 000 mots (4 chiffres) avec `crunch`
- Attaque Hydra sur une authentification HTTP Basic
- Découverte du mot de passe : `1234`
- Configuration Fail2ban (jail `http-auth`) → bannissement de l'IP après 3 échecs

**Résultats** :
- IP `192.168.1.20` bannie
- 2618 tentatives échouées bloquées

![Hydra - mot de passe trouvé](./images/hydra-password-found.png)
![Fail2ban - IP bannie](./images/fail2ban-status.png)

---

### 2. 📧 Serveur mail Postfix (SMTP brut)
*Comprendre le protocole SMTP sans client mail*

**Objectif** : Interagir directement avec un serveur mail en ligne de commande.

**Actions réalisées** :
- Installation de Postfix sur Debian 12
- Envoi d'email via session `telnet` (port 25)
- Dialogue SMTP manuel : `HELO`, `MAIL FROM`, `RCPT TO`, `DATA`
- Vérification de la réception avec la commande `mail`

**Résultat** : Email "ceci est un test spam" reçu dans la boîte locale.

![Telnet SMTP](./images/mail-telnet.png)
![Réception mail](./images/mail-reception.png)

---

### 3. 🔍 Détection d'intrusion + firewall nftables
*Durcissement et monitoring réseau*

**Objectif** : Configurer un firewall restrictif et détecter les scans.

**Configuration nftables** :
```nft
table inet mon_filtre {
    chain input {
        type filter hook input priority filter; policy drop;
        icmp type echo-request accept
        ct state established,related accept
    }
}
**🛡️Détection**
Mise en place d'un système de surveillance et de filtrage réseau pour identifier les comportements malveillants.
- **Méthodologie :** Scan Nmap depuis Kali Linux (détection de ports filtrés).
- **Analyse :** Exploitation des logs kernel avec mentions `INTRUSION_DETECTEE`.
- **Tests :** Simulations de tentatives SYN sur ports variés (1132, 5002, 2047, 1310, 6580...).

![Règles nftables](./images/nftables-rules.png)
![Logs intrusion](./images/intrusion-logs.png)

---

### 4. 🌐 Infrastructure Réseau Multisite (Cisco Packet Tracer)
Conception et segmentation d'une architecture réseau complexe.
- **Technologies :** Routage statique & RIP, VLANs et ACLs (Access Control Lists).
- **Services :** DNS, DHCP, SSH.
- **Compétences :** Configuration d'équipements Cisco, isolation des flux, gestion d'adressage IP.

![Topologie Cisco](./images/cisco-vlan.png)

---

### 🖧 5. Serveur DNS (Bind9)
Installation et configuration d'un service de résolution de noms interne sur Debian.
- **Configuration :** Serveur DNS maître.
- **Gestion :** Zones "Forward" et "Reverse" pour un réseau local.

![Configuration DNS](./images/dns-config.png)

---

### 🎮 6. Développement Software & Jeux

#### **Bataille Navale en C** (Visual Studio)
Jeu en mode terminal avec gestion complète de la logique de jeu.
- **Fonctionnalités :** Mode Joueur vs Ordinateur, gestion des coups et vérification du placement des navires.
- [🔗 Code source du projet](Lien-vers-ton-repo)

#### **Jeu Unity + IA** (En cours) 🏗️
Développement d'un agent intelligent en C#.
- **Objectif :** Intégration d'un agent IA (pathfinding et comportements autonomes).
- [📹 Voir la démonstration vidéo](Lien-vers-ta-video)

---

## 🎓 Formations

| Diplôme | Établissement | Année |
| :--- | :--- | :--- |
| **1re année cycle ingénieur du numérique** | ESAI, Angers | 2025 - 2026 |
| **Tronc commun cycle ingénieur** | ENSPD, Douala | 2023 - 2025 |
| **Licence 1 Biochimie** | Université de Douala | 2022 - 2023 |
| **Baccalauréat** | Douala, Cameroun | 2022 |

---

### 🗣️ Langues
* **Français :** Natif
* **Anglais :** Intermédiaire avancé
* **Allemand :** Notions de base

### 🤝 Engagement Citoyen
* **Bénévole COP 1 – Angers** : Participation active aux initiatives locales.

---

## 📂 Ressources
* [📄 Télécharger mon CV (PDF)](./Lien-vers-ton-cv.pdf)
* [💻 Mon profil GitHub](https://github.com/ton-pseudo)
