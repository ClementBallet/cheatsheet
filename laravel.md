# CREE UN PROJET LARAVEL 5.4

sous bash dans le dossier de projet :
composer create-project --prefer-dist laravel/laravel name "5.4.*"

créer un virtual host dans wamp
Redémarrer le dns

créer une base de données dans phpmyadmin

changer les paramètres dans .env du dossier du projet

en 5.4, je modifie le config>database.php pour changer utf8-mb4 en utf8
je crée mes migrations et mes models
```
php artisan make:model Model -m
```
Model au singulier avec une majuscule
-m = model avec migration

je crée mes controllers (tjrs faire avant les routes)
```
php artisan make:controller NameController --resource
```
Name au pluriel si ça concerne plusieurs choses

je crée mes vues à la main

je crée mon authentification
```
php artisan make:auth
```

je crée mes routes à la main dans web.php

je remplis les migrations
je migre

```
php artisan migrate
```

je lie mes méthodes de controllers à mes vues

je mets en place mes relations (one to one,..) dans les models
ne pas oublier le protected $fillable

je rempli mes vues (mettre layouts dans dossier layouts)
je remplis mes controlleur

accessor permet de modifier le donnée avant de l'afficher
public function getNameAttribute

mutator permet de modifier la donnée avant de l'enregistrer dans la bdd
public function setNameAttribute