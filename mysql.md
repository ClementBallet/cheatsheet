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
|Afficher la structure de la table|`desc [table];` ou `describe [table]`|
|Lister les index d'une table|`show index from [table];`|
|Exporter une base de données (plus d'infos [ici](http://stackoverflow.com/a/21091197/1815847))|`mysqldump -u [username] -p [database] > db_backup.sql`|
|Importer une base de données (plus d'infos [ici](http://stackoverflow.com/a/21091197/1815847))|`mysql -u [username] -p -h localhost [database] < db_backup.sql`|
|Se déconnecter du gestionnaire de base de données|`exit;`|

### Fonctions utilisateur

|Description|Commande|
|-----------|--------|
|Lister tous les utilisateurs|`SELECT User,Host FROM mysql.user;`|
|Créer un nouvel utilisateur|`CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';`|
|Donner tous les privilèges d'accés à un utilisateur pour toutes les tables \(\*\)|`GRANT ALL ON database.* TO 'user'@'localhost';`|

### Créer des éléments dans la base de données

|Description|Commande|
|-----------|--------|
|Créer une nouvelle table avec des colonnes|`CREATE TABLE [table] ([column] VARCHAR(120), [another-column] DATETIME);`|
|Ajouter une colonne à une table existante|`ALTER TABLE [table] ADD COLUMN [column] VARCHAR(120);`|
|Ajouter une colonne avec un ID unique auto-incrémenté|`ALTER TABLE [table] ADD COLUMN [column] int NOT NULL AUTO_INCREMENT PRIMARY KEY;`|
|Insérer un enregistrement|`INSERT INTO [table] ([column], [column]) VALUES ('[value]', '[value]');`|
|Fonction MySQL pour ajouter la date et l'heure dans l'enregistrement|`NOW()`|

### Manipuler la base de données

|Description|Commande|
|-----------|--------|
|Renommer une `[table]`|`ALTER TABLE [table] RENAME [new_name]`|
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
|Effacer tous les enregistrements d'une table sans remise à zéro de l'auto-incrémentation|`DELETE FROM [table];`|
|Effacer tous les enregistrements d'une table avec remise à zéro de l'auto-incrémentation|`TRUNCATE TABLE [table];`|
|Supprimer les colonnes d'une table|`ALTER TABLE [table] DROP COLUMN [column];`|
|Supprimer une table|`DROP TABLE [table];`|
|Supprimer une base de données|`DROP DATABASE [database];`|

### Fonctions d'agrégation

|Description|Commande|
|-----------|--------|
|Sélectionner des enregistrements sans doublons|`SELECT distinct name, email, acception FROM owners WHERE acception = 1 AND date >= 2015-01-01 00:00:00`|
|Calculer la somme des données des enregistrements|`SELECT SUM([column]) FROM [table];`|
|Calculer la somme des données de `[column]` et grouper par `[category-column]`|`SELECT [category-column], SUM([column]) FROM [table] GROUP BY [category-column];`|
|Récupérer la valeur maximale dans `[column]`|`SELECT MAX([column]) FROM [table];`|
|Récupérer la valeur minimale dans `[column]`|`SELECT MIN([column]) FROM [table];`|
|Récupérer la valeur moyenne dans `[column]`|`SELECT AVG([column]) FROM [table];`|
|Récupérer l'arrondi à 2 chiffres de décimal de la valeur moyenne de `[column]` et grouper par `[category-column]`|`SELECT [category-column], ROUND(AVG([column]), 2) FROM [table] GROUP BY [category-column];`|

### Requêtes avec plusieurs tables

|Description|Commande|
|-----------|--------|
|Sélectionner des enregistrements de plusieurs tables|`SELECT [table1].[column], [table1].[another-column], [table2].[column] FROM [table1], [table2];`|
|Sélectionner et combiner des enregistrements de plusieurs tables|`SELECT * FROM [table1] INNER JOIN [table2] ON [table1].[column] = [table2].[column];` (Jointures: INNER JOIN, LEFT JOIN, RIGHT JOIN)|
|Renommer une colonne ou une table en utilisant un _alias_|`SELECT [table1].[column] AS alias, [table2].[column] AS alias FROM [table1], [table2];`|
