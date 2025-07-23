# Présentation
Ce fichier contient une introduction à Git et ses différentes commandes pour une utilisation basique. 

**Sommaire**
- [Git workflow](#Git-workflow)
- [Commandes](#Commandes)
- [Initialisation](##Initialisation)
- [Commandes basiques](##Commandes-basiques)
- [Branches](##Branches)
- [Merge des branches](##Merge-des-branches)
- [Avec git merge](##avec-git-merge)
- [Avec git rebase](##avec-git-rebase)
- [Git ignore](#Git-ignore-(.gitingore))

**Ressources**
- [https://git-scm.com/]
- [https://roadmap.sh/mlops]
- [https://cs.fyi/guide/git-cheatsheet] Cheat sheet 
- [https://www.youtube.com/watch?v=vA5TTz6BXhY&ab_channel=TraversyMedia]
– [https://www.youtube.com/@philomatics]

# Git workflow
![alt text](<../images/git workflow.jpg>)

# Commandes

## Initialisation 

````
# Configuration
git config --global user.name "Nom d'utilisateur"
git config --global user.mail <adresse@>
# Pour voir l'utilisateur actuel
git config --global user.name

# Renommer la branche master par main
git config --global init.defaultBranch main

# Pour creer un nouveau local repo depuis un dossier
git init

# Pour cloner un Remote repo existant
git clone <URLGit>
````

## Commandes basiques
````
# Statut des fichiers dans la branche
git status

# Ajouter un fichier dans la stagin area
git add <file(s)>
git add .  # Pour ajouter tous les fichiers

# Commit les modifications de la staging area vers le repo local
git commit -m "commit message"

# Ajouter les modifications au remote repo
git push origin <branche>

# Raccourci
git add <file> && git commit -m "commit message"


# Pour récuperer des modifications depuis le remote repo 
git pull # correspond à un git fetch + git merge

# Pour récupérer les changements du remote repo sans les appliquer (maj des pointeur git)
git fetch
````

## Branches
````
# Lister les branches
git branch
git branch -r # branches du remote repo
git branch -a # branches du local repo

# Créer une branche
git branch <branch_name>

# Changer de branche
git checkout <branche>

# Merge les branches
git merge

# Supprimer une branche
git branch -d <branch_name>  # Suppression de la branche locale
git push origin  --delete <branch_name>  # Suppression sur la branche distante

# Pour supprimer les branches locales déjà supprimées sur le remote repo
git fetch --prune 
````

# Merge des branches
## Avec git merge
````
# Pour merge sur le main
git fetch origin (vérifie que tout est à jour)
git checkout main
# Si besoin de mettre à jour la branche main
git pull origin main
git merge <branche_name>

# Résolution de conflit si nécessaire
git add <Conflit files>  # Après correction
git commit -m "commit message"

git push origin main

# si besoin de supprimer la branche
git branch -d <branche_name>  # Supprime localement
git push origin --delete <branche_name>  # Supprime à distance

````

## Avec git rebase
Ressources : [https://www.youtube.com/watch?v=DkWDHzmMvyg&ab_channel=Philomatics]

````
# Pour faire un merge sur le main
git checkout main
git pull origin main # Recupère les fichiers du remote repo
git rebase main  
# Si besoin d'annuler
git rebase --abort

# Correction des conflits (si nécessaire)
# Après correction
git add <Conflict files>
git commit -m "commit message"
git push origin main # Résolution des conflits
git rebase --continue
````


# Git ignore (.gitignore)
Exemple de fichier 
````
# ignore txt files
*.txt

# ignore workspace files (vscode)
*.code-workspace

# ignore files in data directory
**/DATA/

# ignore unnecessary repo
__pycache__/
````