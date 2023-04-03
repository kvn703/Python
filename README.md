# Workshop - Introduction to Django

Durant ce Workshop, vous allez apprendre à créer une application web avec le framework Django.

## Qu'estce que Django ?

Django est un framework web open source écrit en Python. Il est conçu pour favoriser le développement rapide et le design propre et pragmatique. Il encourage la bonne pratique de développement et favorise un code DRY (Don't Repeat Yourself). 

# Step 0 : Installation

Installer Django en suivant ce lien : `https://docs.djangoproject.com/en/4.1/topics/install/`

Lorsque vous avez terminé, vous pouvez vérifier que Django est bien installé en écrivant : `python -m django --version` dans votre terminal.

Si vous avez une erreur, vous pouvez suivre ce lien : `https://docs.djangoproject.com/en/4.1/topics/install/#installing-official-release`

# Step 1 : Initiation Django + Créer un projet

Pour créer un projet, vous devez écrire dans votre terminal : `django-admin startproject mysite` , où "mysite" est le nom de votre site.

Une fois que vous avez terminé, vous pouvez vérifier que votre projet est bien créé en écrivant : `tree` dans votre terminal et avoir le résultat suivant : 

```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```

Vous pouvez ensuite vous rendre dans le dossier de votre projet avec la commande : `cd mysite`

### Explication des fichiers

- `manage.py` : C'est un script qui permet de gérer votre projet. Vous pouvez l'utiliser pour lancer un serveur web, créer des applications, etc.
- `mysite/` : C'est un dossier qui contient votre projet. Il est nommé comme le dossier parent.
- `mysite/__init__.py` : C'est un fichier vide qui indique à Python que ce dossier doit être considéré comme un package.
- `mysite/settings.py` : C'est le fichier de configuration de votre projet. Il contient notamment la liste des applications installées.
- `mysite/urls.py` : C'est le fichier de routage de votre projet. Il contient la liste des URL de votre projet.
- `mysite/asgi.py` : C'est un point d'entrée pour les serveurs web compatibles avec ASGI.
- `mysite/wsgi.py` : C'est un point d'entrée pour les serveurs web compatibles avec WSGI.

# Step 2 : Lancer le serveur

Pour lancer le serveur, vous devez écrire dans votre terminal : `python manage.py runserver` . Vous pouvez ensuite vous rendre sur `http://(l'adresse IP de votre machine):8000/` pour voir votre site.

### Changer le port du serveur

Par défaut, le serveur tourne sur le port 8000. Maintenant, nous souhaitons le faire tourner sur le port `4242`.