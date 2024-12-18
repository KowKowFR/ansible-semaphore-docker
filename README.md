# Project Name

Ce projet utilise `docker-compose` pour déployer Semaphore (un gestionnaire de flux de travail pour Ansible), MySQL, et Ansible. Semaphore gère les exécutions d'Ansible, les workflows et les tâches automatiques, tandis que MySQL sert de base de données pour Semaphore. Ansible est utilisé pour déployer les playbooks Ansible dans un environnement isolé.

## Prérequis

Avant de commencer, assurez-vous d'avoir installé `docker` et `docker-compose` sur votre machine.

1. **Docker** :
   - Si ce n'est pas déjà fait, installez Docker à l'aide de ces instructions : [Docker Installation](https://docs.docker.com/get-docker/).

2. **Docker Compose** :
   - Assurez-vous que Docker Compose est installé. Vous pouvez le faire en utilisant la commande suivante :
     ```bash
     docker-compose --version
     ```

## Configuration

1. **Création du fichier `.env`** :
   - Créez un fichier `.env` dans le répertoire où se trouve votre `docker-compose.yml` avec les informations suivantes :

   ```env
   MYSQL_RANDOM_ROOT_PASSWORD=yes
   MYSQL_DATABASE=semaphore
   MYSQL_USER=semaphore
   MYSQL_PASSWORD=semaphore

   SEMAPHORE_DB_USER=semaphore
   SEMAPHORE_DB_PASS=semaphore
   SEMAPHORE_DB_HOST=mysql
   SEMAPHORE_DB_PORT=3306
   SEMAPHORE_DB_DIALECT=mysql
   SEMAPHORE_DB=semaphore
   SEMAPHORE_PLAYBOOK_PATH=/tmp/semaphore/
   SEMAPHORE_ADMIN_PASSWORD=changeme
   SEMAPHORE_ADMIN_NAME=admin
   SEMAPHORE_ADMIN_EMAIL=admin@localhost
   SEMAPHORE_ADMIN=admin
   SEMAPHORE_ACCESS_KEY_ENCRYPTION=gs72mPntFATGJs9qK0pQ0rKtfidlexiMjYCH9gWKhTU=
   TZ=UTC
