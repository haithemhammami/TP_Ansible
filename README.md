# Déploiement de l'application Appli-Locations-Voitures avec Ansible

Ce projet utilise Ansible pour configurer une infrastructure complète (serveur web, base de données, et serveur applicatif) et déployer l'application **Appli-Locations-Voitures**.

## Pré-requis

- Une machine de contrôle avec Ansible installé (Ubuntu/Debian recommandé).
- Accès SSH à vos machines cibles (serveur web, serveur de base de données, et serveur applicatif).
- Les machines cibles doivent utiliser Ubuntu ou Debian.

## Structure du projet

tp-ansible/
├── playbooks/
│   ├── webserver.yml
│   ├── database.yml
│   ├── appserver.yml
│   ├── deploy.yml
├── roles/
│   ├── webserver/
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   └── templates/
│   │       └── virtualhost.conf.j2
│   ├── database/
│   │   └── tasks/
│   │       └── main.yml
│   └── appserver/
│       └── tasks/
│           └── main.yml
├── inventory/
│   └── hosts
└── README.md


## Étapes pour déployer

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/
   cd TP_Ansible

2. **Configurer l'inventaire**
Éditez le fichier inventory/hosts et ajoutez les adresses IP ou les noms d’hôtes des machines cibles.

[webserver]
192.168.1.10

[database]
192.168.1.20

[appserver]
192.168.1.30

3. **Lancer les playbooks**

Lancez les playbooks dans l'ordre suivant :

**Serveur web :**
ansible-playbook -i inventory/hosts playbooks/webserver.yml

**Base de données :**
ansible-playbook -i inventory/hosts playbooks/database.yml

**Serveur applicatif :**
ansible-playbook -i inventory/hosts playbooks/appserver.yml

**Déploiement de l'application :**
ansible-playbook -i inventory/hosts playbooks/deploy.yml


4. **Accéder au projet Une fois déployé, ouvrez votre navigateur à l’adresse suivante : (exemple)**

http://192.168.1.10

Haithem Hammami

Projet utilisé
Appli-Locations-Voitures
https://github.com/EmericDe/Appli-Locations-Voitures