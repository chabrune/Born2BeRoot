# Born2beRoot - Configuration d'un Serveur Virtuel

Un projet d'administration système visant à créer et configurer une machine virtuelle sous Debian ou Rocky Linux.

## 🎯 Objectifs Principaux

- Création d'une machine virtuelle sous VirtualBox/UTM
- Configuration d'un système d'exploitation minimal sans interface graphique
- Mise en place de règles de sécurité strictes

## 🔒 Configuration Requise

### Système
- Debian (dernière version stable) ou Rocky Linux
- Partitionnement LVM avec minimum 2 partitions chiffrées
- Hostname : login42

### Sécurité
- SSH actif sur le port 4242 uniquement
- Configuration UFW/firewalld avec port 4242 ouvert
- Politique de mots de passe forte :
  - Expiration tous les 30 jours
  - Minimum 10 caractères
  - Majuscule, minuscule, chiffre obligatoires
  - Maximum 3 caractères identiques consécutifs
  - Pas de nom d'utilisateur dans le mot de passe

### Configuration sudo
- Limite de 3 essais d'authentification
- Archivage des commandes dans /var/log/sudo/
- Mode TTY activé
- Chemins d'accès restreints

## 📊 Script de Monitoring

Le script monitoring.sh affiche toutes les 10 minutes :
- Architecture système et version kernel
- Processeurs (physiques et virtuels)
- Utilisation mémoire et disque
- Charge CPU
- Dernier redémarrage
- État LVM
- Connexions actives
- Utilisateurs connectés
- Adresse IPv4 et MAC
- Commandes sudo exécutées

---
*Projet réalisé dans le cadre du cursus de l'école 42*
