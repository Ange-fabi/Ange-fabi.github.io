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
