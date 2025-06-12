# 📦 Déploiement d’un blog WordPress avec Docker Compose

## 🎯 Objectif

Ce projet consiste à déployer un blog WordPress avec sa base de données MySQL sous forme de microservices, en utilisant Docker Compose. L’objectif est de fournir une solution facilement réutilisable et portable pour les développeurs et testeurs.

## 🚀 Lancement rapide

### 1. Cloner ce dépôt

```bash
git clone https://github.com/Tostenn/wordpress-docker.git
cd wordpress-docker
````

### 2. Lancer les services

```bash
docker-compose up -d
```

### 3. Accéder à l’application

Ouvrez votre navigateur à l’adresse :
👉 [http://localhost:8000](http://localhost:8000)

---

## 🧱 Structure du projet

* **`wordpress`** : Conteneur WordPress (CMS)
* **`db`** : Conteneur MySQL (base de données)
* **`db_data`** : Volume Docker pour persister les données MySQL

---

## ⚙️ À propos du fichier `docker-compose.yaml`

Le fichier `docker-compose.yaml` définit deux services :

### 🔹 Service `db`

* Image utilisée : `mysql:5.7`
* Stockage persistant avec le volume `db_data`
* Variables d’environnement :

  * `MYSQL_ROOT_PASSWORD`
  * `MYSQL_DATABASE`
  * `MYSQL_USER`
  * `MYSQL_PASSWORD`

### 🔹 Service `wordpress`

* Image utilisée : `wordpress:latest`
* Dépend du service `db` (avec `depends_on`)
* Port exposé : `8000` (accessible via `localhost:8000`)
* Variables d’environnement pour connecter WordPress à MySQL :

  * `WORDPRESS_DB_HOST`
  * `WORDPRESS_DB_NAME`
  * `WORDPRESS_DB_USER`
  * `WORDPRESS_DB_PASSWORD`
