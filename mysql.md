# **MYSQL**

Pour apprendre :

- http://www.sqlteaching.com/
- https://www.codecademy.com/courses/learn-sql

Outils et logiciels :

- [DataGrip](https://www.jetbrains.com/datagrip/)
- [Sequel Pro](http://www.sequelpro.com/)




## Commandes


### Accéder à la base de données

|Description|Commande|
|-----------|--------|
|Accéder au gestionnaire de base de données|`mysql -u [username] -p;`|
|Afficher la liste des bases de données|`show databases;`|
|Accéder directement à une base de données| `mysql -u [username] -p [database]`|
|Créer une nouvelle base de données|`create database [database];`|
|Utiliser une base de données|`use [database];`|
|Savoir sur quelle base de données on est|`select database();`|

### Manipuler la base de données

|Description|Commande|
|-----------|--------|
|Lister les tables|`show tables;`|
|Afficher la structure de la table|`describe [table];`|
|Lister les index d'une table|`show index from [table];`|
|Créer une nouvelle table avec des colonnes|`CREATE TABLE [table] ([column] VARCHAR(120), [another-column] DATETIME);`|
|Ajouter une colonne à une table existante|`ALTER TABLE [table] ADD COLUMN [column] VARCHAR(120);`|
|Ajouter une colonne avec un ID unique auto-incrémenté|`ALTER TABLE [table] ADD COLUMN [column] int NOT NULL AUTO_INCREMENT PRIMARY KEY;`|
|Insérer un enregistrement|`INSERT INTO [table] ([column], [column]) VALUES ('[value]', [value]');`|
