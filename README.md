# Blog WordPress avec Docker Compose

## Objectif
Déployer un blog WordPress et sa base de données MySQL avec Docker Compose.

## Lancement

1. Cloner ce dépôt
2. Lancer les services Docker :

```bash
docker-compose up -d
```

3. Accéder à WordPress via : [http://localhost:8000](http://localhost:8000)

## Structure

- `wordpress`: Conteneur WordPress
- `db`: Conteneur MySQL
- `db_data`: Volume Docker pour stocker les données MySQL
