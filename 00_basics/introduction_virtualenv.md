# Création d'environnement virtuel avec virtualenv

venv est la méthode standard de création d'environnement pour Python. Il est possible d'utiliser uv ou Poetry pour une utilisation plus avancée.

**Ressources**
- [https://docs.python.org/3/library/venv.html]


## Créer un environnement 

Prérequis : 
- Avoir une version Python installée
- Installer un gestionnaire d'environnement (pip et virtualenv)
- Avoir un fichier requirements.txt

pip est le gestionnaire de paquets pour Python

````
python -m pip install --upgrade pip
pip install virtualenv
````

Création de l'environnement à partir du répertoire du projet
````
# Exemple pour une version 3.12
cd path/project
python3.12 -m venv env_name

# Avec une seule commande
python3.12 -m venv /path/to/new/env/env_name

# Avec windows
python3.12 -m venv C:\path\to\new\virtual\env_name
````

Activer l'environnement et installer les packages avec un requirements.txt
````
# Windows
env_name\Scripts\activate

# Linux et macos
source venv/bin/activate

# Avec un fichier requirements.txt
python3.12 -m pip install -r requirements.txt

# Desactiver l'enviromment
deactivate
````

Exemple simple de fichier requirements.txt
````
# requirements.txt pour l'environnement env_name, python 3.12
numpy
pandas
scikit-learn
````

Installer les packages sans requirements.txt
````
# Windows
env_name\Scripts\activate

# Linux et macos
source venv/bin/activate

# sans fichier requirements.txt
pip install numpy pandas scikit-learn

# Pour afficher les packages
pip freeze

# Créer un requirements.txt a partir de l'environnement
pip freeze > requirements.txt

# Desactiver l'enviromment
deactivate
````
