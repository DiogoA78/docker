# Projet Docker 1 - Stack Applicative WordPress et MariaDB
Ce README documente les étapes et configurations réalisées pour la mise en place d'un environnement Docker comprenant WordPress et MariaDB, telles que discutées et élaborées tout au long de notre conversation.

## Aperçu du Projet
Ce projet implique la création de conteneurs Docker pour exécuter une instance de WordPress en tant que frontend et MariaDB comme backend pour la gestion des données. Les conteneurs sont configurés pour fonctionner ensemble, offrant une plateforme pour héberger un site WordPress.

## Configuration de MariaDB
Un conteneur Docker a été créé pour exécuter MariaDB.
Les configurations clés, comme le mot de passe root, ont été définies pour assurer la sécurité et la connectivité.
Le port standard de MariaDB (3306) a été exposé pour permettre la communication entre le conteneur et l'hôte.

## Configuration de WordPress
Un conteneur Docker distinct pour WordPress a été configuré.
WordPress est configuré pour se connecter à la base de données MariaDB.
Le port 80 a été exposé pour permettre l'accès au site WordPress depuis un navigateur web.

## Docker Compose
Docker Compose a été utilisé pour orchestrer les conteneurs WordPress et MariaDB, facilitant ainsi leur gestion simultanée.
La configuration de Docker Compose comprend la définition des services, des ports exposés, et des réseaux.

## Réseaux Docker
Deux réseaux Docker distincts ont été créés pour séparer les préoccupations de sécurité et de connectivité.
frontend_network est utilisé exclusivement par le conteneur WordPress.
backend_network est partagé par les conteneurs WordPress et MariaDB, permettant une communication sécurisée entre le frontend et le backend.
