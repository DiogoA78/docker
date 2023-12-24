# Projet Docker 1 - Stack Applicative WordPress et MariaDB
Ce README documente les étapes et configurations réalisées pour la mise en place d'un environnement Docker comprenant WordPress et MariaDB, telles que discutées et élaborées tout au long de notre conversation.

### Aperçu du Projet
Ce projet implique la création de conteneurs Docker pour exécuter une instance de WordPress en tant que frontend et MariaDB comme backend pour la gestion des données. Les conteneurs sont configurés pour fonctionner ensemble, offrant une plateforme pour héberger un site WordPress.

### Configuration de MariaDB
Un conteneur Docker a été créé pour exécuter MariaDB.
Les configurations clés, comme le mot de passe root, ont été définies pour assurer la sécurité et la connectivité.
Le port standard de MariaDB (3306) a été exposé pour permettre la communication entre le conteneur et l'hôte.

### Configuration de WordPress
Un conteneur Docker distinct pour WordPress a été configuré.
WordPress est configuré pour se connecter à la base de données MariaDB.
Le port 80 a été exposé pour permettre l'accès au site WordPress depuis un navigateur web.

### Docker Compose
Docker Compose a été utilisé pour orchestrer les conteneurs WordPress et MariaDB, facilitant ainsi leur gestion simultanée.
La configuration de Docker Compose comprend la définition des services, des ports exposés, et des réseaux.

### Réseaux Docker
Deux réseaux Docker distincts ont été créés pour séparer les préoccupations de sécurité et de connectivité.
frontend_network est utilisé exclusivement par le conteneur WordPress.
backend_network est partagé par les conteneurs WordPress et MariaDB, permettant une communication sécurisée entre le frontend et le backend.


# Projet Docker 2 - Cluster Elasticsearch avec Kibana

## Structure du Projet
Diogo_Aroune/
│
├── docker-compose.yml
├── .env
├── es-cluster/
├── elasticsearch.yml
└── kibana.yml
Fichier .env

À la racine du projet (`Diogo_Aroune/`), créez un fichier `.env` pour définir les variables
d'environnement utilisées dans le `docker-compose.yml`.
Contenu du fichier `.env` :
ES_VERSION=8.11.3

## Configuration du Cluster Elasticsearch

### Elasticsearch.yml
Dans le répertoire `es-cluster/`, créez un fichier `elasticsearch.yml` qui contiendra la
configuration spécifique pour les noeuds Elasticsearch.

### Kibana.yml
Toujours dans le répertoire `es-cluster/`, créez un fichier `kibana.yml` pour la configuration
de Kibana.

## Docker-compose.yml
À la racine du projet, créez un fichier `docker-compose.yml` avec la configuration suivante :
- Trois services Elasticsearch (es01, es02, es03) qui forment un cluster.
- Un service Kibana (kibana) connecté au cluster Elasticsearch.
- Assurez-vous que les noeuds Elasticsearch utilisent les fichiers de configuration
appropriés.
- Configurez les variables d'environnement nécessaires.
- 
## Exécution
Pour démarrer le cluster :
1. Ouvrez un terminal.
2. Naviguez jusqu'au répertoire `Diogo_Aroune/`.
3. Exécutez la commande :
docker-compose up
4. Vérifiez que le cluster Elasticsearch et le service Kibana sont opérationnels.
Remarques Importantes
- La configuration du cluster Elasticsearch doit spécifier trois noeuds (es01, es02, es03).
- Les données doivent être persistantes.
- Le service Kibana doit être configuré pour se connecter à l'un des noeuds Elasticsearch.
- Configurez un réseau sur lequel tous les services seront connectés.
