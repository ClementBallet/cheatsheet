# GIT

## Liens Utiles

- [Git Cheatsheet de GitHub](https://services.github.com/on-demand/downloads/fr/github-git-cheat-sheet.pdf)
- Tutoriel interactif pour les débutants: http://try.github.io/
- Quelques tips de pro : https://ochronus.com/git-tips-from-the-trenches/

## Commandes

#### Configuration

|Description|Commande|
|-----------|--------|
|Savoir dans quel dossier git se stitue|`which git`|
|Connaître la version de git installée|`git --version`|
|Créer un alias (raccourci) pour `git status`|`git config --global alias.st status`|
|Définir le nom que vous voulez associer à tous vos commits|`git config --global user.name "[nom]"`|
|Définir l'email que vous voulez associer à tous vos commit|`git config --global user.email "[adresse email]"`|
|Activer la colorisation de la sortie en ligne de commande|`git config --global color.ui auto`|

#### Créer un dépôt

|Description|Commande|
|-----------|--------|
|Crée un dépôt local à partir du nom spécifié|`git init [nom-du-projet]`|
|Télécharge un projet et tout son historique de versions|`git clone [url]`|

#### Faire des changements (add, commit, reset, remove)

|Description|Commande|
|-----------|--------|
|Lister tous les nouveaux fichiers et les fichiers modifiés à commiter|`git status`|
|Afficher les modifications de fichiers locaux qui ne sont pas encore indexées (pas ajoutés pour le versionnage)|`git diff`|
|Ajouter un fichier, en préparation pour le versionnage|`git add [fichier]`|
|Ajouter tous les fichiers, en préparation pour le versionnage|`git add .`|
|Afficher les différences de fichier entre la version indexée et la dernière version du dépôt git|`git diff --staged`|
|Enlever le fichier de l'index de versionnage, mais conserver son contenu|`git reset [fichier]`|
|Faire un commit avec un message|`git commit -m "[message descriptif]"`|
|Ajouter et faire un commit en une commande|`git commit -am "[message descriptif]"`|
|Supprimer le fichier du répertoire de travail et met à jour l'index|`git rm [file]`|
|Supprimer le fichier du système de suivi de version mais le préserve localement|`git rm --cached [fichier]`| 
|Renommer le fichier et préparer le changement pour un commit |`git mv [fichier-nom] [fichier-nouveau-nom]`|


