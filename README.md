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

# Step 3 : Création de l’application Polls

Une fois que vous avez compris comment lancer votre serveur Django et que vous avez compris les différents fichiers, nous allons créer notre première application.

## Qu'est ce qu'une application ?

Une application est un ensemble de fonctionnalités qui peuvent être utilisées dans plusieurs projets. Par exemple, une application de blog peut être utilisée dans plusieurs projets.

## Créer une application Polls

Pour créer une application, vous devez écrire dans votre terminal : `python manage.py startapp polls` , où "polls" est le nom de votre application.

## Ecrire une vue

Une fois que vous aviez créé votre application, vous devez écrire une vue. Une vue est une fonction qui prend une requête en entrée et renvoie une réponse.
Tout d'abord, nous allons écrire un script dans le fichier `polls/views.py` qui va renvoyer un message.

`Hello, world. You're at the polls index.".`

''' CONSEIL : Faites bien appel au bon module d'importation '''

Une fois réalisé, vous pouvez lancer votre serveur et vous rendre sur la page web pour voir le résultat. 

EN cas de succès, vous devriez avoir le message suivant : `Hello, world. You're at the polls index.`

# Step 4 : Création d’une base de données

## Qu'est ce qu'une base de données ?

Une base de données est un ensemble de données organisées de manière à ce qu'elles puissent être facilement consultées, modifiées ou supprimées. Une base de données est un outil très important pour stocker des données.

## Créer un super utilisateur

Pour créer un super utilisateur, vous devez écrire dans votre terminal : 

`python manage.py createsuperuser` 

Vous devez ensuite rentrer un nom d'utilisateur, une adresse mail et un mot de passe.

## Accéder à l'interface d'administration

Pour accéder à l'interface d'administration, vous devez vous rendre sur `http://(l'adresse IP de votre machine):8000/admin/`.

Vous devez ensuite rentrer le nom d'utilisateur et le mot de passe que vous avez créé précédemment.