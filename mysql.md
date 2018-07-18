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
|Lister les tables|`show tables;`|
|Afficher la structure de la table|`describe [table];`|
|Lister les index d'une table|`show index from [table];`|
|Exporter une base de données (plus d'infos [ici](http://stackoverflow.com/a/21091197/1815847))|`mysqldump -u [username] -p [database] > db_backup.sql`|
|Importer une base de données (plus d'infos [ici](http://stackoverflow.com/a/21091197/1815847))|`mysql -u [username] -p -h localhost [database] < db_backup.sql`|
|Se déconnecter du gestionnaire de base de données|`exit;`|

### Créer des éléments dans la base de données

|Description|Commande|
|-----------|--------|
|Créer une nouvelle table avec des colonnes|`CREATE TABLE [table] ([column] VARCHAR(120), [another-column] DATETIME);`|
|Ajouter une colonne à une table existante|`ALTER TABLE [table] ADD COLUMN [column] VARCHAR(120);`|
|Ajouter une colonne avec un ID unique auto-incrémenté|`ALTER TABLE [table] ADD COLUMN [column] int NOT NULL AUTO_INCREMENT PRIMARY KEY;`|
|Insérer un enregistrement|`INSERT INTO [table] ([column], [column]) VALUES ('[value]', [value]');`|
|Fonction MySQL pour ajouter la date et l'heure dans l'enregistrement|`NOW()`|

### Manipuler la base de données

|Description|Commande|
|-----------|--------|
|Sélectionner tous les enregistrements d'une table|`SELECT * FROM [table];`|
|Sélectionner une partie des enregistrements|`SELECT [column], [another-column] FROM [table];`|
|Modifier le nom d'une colonne sur la sélection|`SELECT [column] AS [custom-column] FROM [table];`|
|Compter le nombre d'enregistrements|`SELECT COUNT([column]) FROM [table];`|
|Sélectionner, compter et regrouper des enregistrements|`SELECT *, (SELECT COUNT([column]) FROM [table]) AS count FROM [table] GROUP BY [column];`|
|Sélectionner des enregistrements selon des paramètres|`SELECT * FROM [table] WHERE [column] = [value];` (Sélecteurs: `<`, `>`, `!=`; combiner plusieurs sélecteurs avec `AND` et `OR`)|
|Sélectionner des enregistrements contenant `[value]`|`SELECT * FROM [table] WHERE [column] LIKE '%[value]%';`|
|Sélectionner des enregistrements commençant par `[value]`|`SELECT * FROM [table] WHERE [column] LIKE '[value]%';`|
|Sélectionner des enregistrements commençant par `val` et finissant par `ue`|`SELECT * FROM [table] WHERE [column] LIKE '[val_ue]';`|
|Sélectionner des enregistrement selon un intervalle|`SELECT * FROM [table] WHERE [column] BETWEEN [value1] and [value2];`|
|Sélectionner des enregistrement avec un ordre et une limite|`SELECT * FROM [table] WHERE [column] ORDER BY [column] ASC LIMIT [value];` (Ordre: `DESC`, `ASC`)|
|Afficher par où passe une requête|`EXPLAIN SELECT * FROM [table];`|
|Changer des enregistrement|`UPDATE [table] SET [column] = '[updated-value]' WHERE [column] = [value];`|

### Supprimer des éléments de la base de données

|Description|Commande|
|-----------|--------|
|Effacer des enregistrements|`DELETE FROM [table] WHERE [column] = [value];`|
|Effacer tous les enregistrements d'une table sans effacer la table|`DELETE FROM [table];`|
|Effacer tous les enregistrements d'une table|`TRUNCATE TABLE [table];`|
|Supprimer les colonnes d'une table|`ALTER TABLE [table] DROP COLUMN [column];`|
|Supprimer une table|`DROP TABLE [table];`|
|Supprimer une base de données|`DROP DATABASE [database];`|
