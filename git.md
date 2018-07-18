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


#### Corriger des erreurs et gérer l'historique des corrections

|Description|Commande|
|-----------|--------|
|Annuler tous les commits après `[commit]`, en conservant les modifications localement|`git reset [commit]`|
|Supprimer tout l'historique et les modifications effectuées après le commit spécifié|`git reset --hard [commit]`|
|Revenir à un commit précis|`git revert [commit]`|


#### Utiliser les branches

|Description|Commande|
|-----------|--------|
|Lister toutes les branches locales dans le dépôt courant|`git branch`|
|Créer une branche|`git branch [nom-de-branche]`|
|Basculer sur la branche spécifiée et mettre à jour le répertoire de travail|`git checkout [nom-de-branche]`|
|Créer et basculer sur la branche spécifiée|`git checkout -b [nom-de-branche]`|
|Supprimer la branche spécifiée|`git branch -d [nom-de-branche]`|
|Renommer une branche|`git branch -m [nom-de-branche] [nouveau-nom-de-branche]`|
|Afficher la liste des branches qui ont été mergées|`git branch --merged`|
|Supprimer les branches qui n'ont pas été mergées|`git branch -D [nom-de-branche]`|


#### Utiliser la fonction merge

|Description|Commande|
|-----------|--------|
|Combine dans la branche courante l'historique de la branche spécifiée|`git merge [nom-de-branche]`|
|Arrêter le merge en cas de conflits|`git merge --abort`|


#### Vérifier l'historique des versions

|Description|Commande|
|-----------|--------|
|
