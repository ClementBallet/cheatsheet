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
|Créer un dépôt local à partir du nom spécifié|`git init [nom-du-projet]`|
|Télécharger un projet et tout son historique de versions|`git clone [url]`|
|Télécharger un projet et tout son historique de versions vers un dossier spécifique|`git clone [url] [path]`|
|Télécharger une branche spécifique|`git clone -b [nom-de-branche] [url]`|


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


#### Référencer un dépôt distant et synchroniser l'historique de versions

|Description|Commande|
|-----------|--------|
|Récupèrer tout l'historique du dépôt nommé|`git fetch [nom-de-depot]`|
|Envoyer tous les commits de la branche locale vers GitHub|`git push origin [nom-de-branche]`|
|Envoyer tous les commits avec push-force|`git push origin [nom-de-branche] --force`|
|Récupèrer tout l'historique du dépôt nommé et incorpore les modifications|`git pull origin [nom-de-branche]`|


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


#### Mettre en suspens des modifications non finies pour y revenir plus tard

|Description|Commande|
|-----------|--------|
|Enregistrer de manière temporaire tous les fichiers sous suivi de version qui ont été modifiés ("remiser son travail")|`git stash "[message descriptif]"`|
|Appliquer une remise et la supprime immédiatement|`git stash pop`|
|Lister toutes les remises|`git stash list`|
|Supprimer la remise la plus récente|`git stash drop`|
|Supprimer toutes les remises|`git stash clear`|


#### Utiliser la fonction merge

|Description|Commande|
|-----------|--------|
|Combine dans la branche courante l'historique de la branche spécifiée|`git merge [nom-de-branche]`|
|Arrêter le merge en cas de conflits|`git merge --abort`|


#### Utiliser la fonction tag

|Description|Commande|
|-----------|--------|
|Afficher toutes les versions released|`git tag`|
|Créer une version release|`git tag v1.0.0`|
|Créer une version release avec un commentaire|`git tag -a v1.0.0 -m "[message descriptif]"`|


#### Utiliser la fonction diff

|Description|Commande|
|-----------|--------|
|


#### Vérifier l'historique des versions

|Description|Commande|
|-----------|--------|
|Afficher l'historique des versions pour la branche courante|`git log`|
|Afficher l'historique des versions pour la branche courante en 1 ligne|`git log --oneline`|
|Afficher l'historique des versions pour la branche courante en 1 ligne avec du SHA-1|`git log --format=oneline`|
|Afficher l'historique des versions pour la branche courante en 1 ligne pour les 3 derniers commits|`git log --oneline -3`|
|Afficher l'historique des versions, y compris les actions de renommage, pour le fichier spécifié|`git log --follow [fichier]`|
|Afficher l'historique des versions selon des paramètres|`git log --author="Sven"`, `git log --grep="Message"`, `git log --until=2013-01-01`, `git log --since=2013-01-01`|
|Afficher les stats et le résumé des commits pour la branche courante|`git log --stat --summary`|
|Afficher l'historique des versions pour la branche courante sous forme de graph|`git log --graph`|
|Afficher les différences de contenu entre deux branches|`git diff [premiere-branche]...[deuxieme-branche]`|
|Afficher les modifications de métadonnées et de contenu inclues dans le commit spécifié|`git show [commit]`|


#### Exclure des fichiers et chemins temporaires

|Description|Commande|
|-----------|--------|
|Un fichier texte nommé `.gitignore` permet d'éviter le suivi de version accidentel pour les fichiers et chemins correspondant aux patterns spécifiés|`*.log build/ temp-*`|
|Lister tous les fichiers exclus du suivi de version dans le projet|`git ls-files --other --ignored --exclude-standard`|

#### Sauvegarder le projet dans une archive

|Description|Commande|
|-----------|--------|
|Créer une archive zip|`git archive --format zip --output filename.zip master`|
