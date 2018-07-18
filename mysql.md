# **MYSQL**

Pour apprendre :

- http://www.sqlteaching.com/
- https://www.codecademy.com/courses/learn-sql

Outils et logiciels :

- [DataGrip](https://www.jetbrains.com/datagrip/)
- [Sequel Pro](http://www.sequelpro.com/)




## Commandes


### Accéder à la base de données

Accéder au gestionnaire de base de données
`mysql -u [username] -p;` (le mot de passe sera demandé)

Voir la liste des bases de données
`show databases;`

Accéder directement à une base de données
`mysql -u [username] -p [database]` (le mot de passe sera demandé)

Créer une nouvelle base de données
`create database [database];`

Utiliser une base de données
`use [database];`

Savoir quelle base de données on utilise actuellement
`select database();`
