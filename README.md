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

# Step 5 : Création d’un modèle

## Qu'est ce qu'un modèle ?

Un modèle est une représentation d'une table de base de données. Il contient les champs et les relations avec d'autres modèles.

## Créer un modèle

Pour créer un modèle, vous devez écrire dans le fichier `polls/models.py` : 
    
    - Créer un modèle `Question` avec les champs suivants : question_text, pub_date (question_text taille max 200)
    - Créer un modèle `Choix` avec les champs suivants : question, choice_text, votes (choice_text taille max 200)

CONSEIL : Faites bien appel au bon module d'importation

## Créer une table

Pour créer une table, tout d'abord modifier le fichier mysite/settings.py : 

    INSTALLED_APPS = [
        'polls.apps.PollsConfig',
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
    ]

En faisant cela, vous avez ajouté l'application Polls à votre projet.

## Créer les migrations

Pour créer les migrations, vous devez écrire dans votre terminal : `python manage.py makemigrations polls` .


    Migrations for 'polls':
     polls/migrations/0001_initial.py
       - Create model Question
       - Create model Choice


Vous pouvez récupérer les migrations dans le dossier `polls/migrations/0001_initial.py` et générer la table dans la base de données.

Exécutez la commande suivante : 

    - python manage.py sqlmigrate polls 0001

Vous devriez avoir le résultat suivant en SQL : 

    BEGIN;
    --
    -- Create model Question
    --
    CREATE TABLE "polls_question" (
        "id" bigint NOT NULL PRIMARY KEY GENERATED BY DEFAULT AS IDENTITY,
        "question_text" varchar(200) NOT NULL,
        "pub_date" timestamp with time zone NOT NULL
    );
    --
    -- Create model Choice
    --
    CREATE TABLE "polls_choice" (
        "id" bigint NOT NULL PRIMARY KEY GENERATED BY DEFAULT AS IDENTITY,
        "choice_text" varchar(200) NOT NULL,
        "votes" integer NOT NULL,
        "question_id" bigint NOT NULL
    );
    ALTER TABLE "polls_choice"
      ADD CONSTRAINT "polls_choice_question_id_c5b4b260_fk_polls_question_id"
        FOREIGN KEY ("question_id")
        REFERENCES "polls_question" ("id")
        DEFERRABLE INITIALLY DEFERRED;
    CREATE INDEX "polls_choice_question_id_c5b4b260" ON "polls_choice" ("question_id");

    COMMIT;

Maintenant, vous pouvez exécuter la commande suivante : `python manage.py migrate` . Vous pouvez maintenant voir la table dans l'interface d'administration.

Donc maintenant, vous avez créé un modèle et une table dans la base de données.*

Si vous voulez ajouter des modifications à votre modèle, vous avez juste à modifier le fichier `polls/models.py` et exécuter la commande suivante :

`python manage.py makemigrations polls`. 

Vous pouvez ensuite exécuter la commande suivante :

`python manage.py migrate` .

# Step 6 : Création d’une API avec le shell

## Qu'est ce qu'une API ?

Une API est une interface de programmation qui permet de communiquer avec un logiciel. Une API est un outil très important pour communiquer avec un logiciel.

Pour accéder à l'interface de programmation, vous devez écrire dans votre terminal : 
    
`python manage.py shell` .

Une fois dans le terminal, vous allez manipuler les objets de votre base de données.

### Créer un objet

Pour créer un objet, vous devez écrire dans le terminal : 
    
    - Créer un objet `Question` avec les champs suivants : "What is the question", à la date d'aujourd'hui
    - Créer un objet `Question` avec les champs suivants : "What time is it ?", à la date d'aujourd'hui
    - Créer un objet `Question` avec les champs suivants : "What is the answer ?", à la date d'aujourd'hui

Pensez à sauvegarder vos objets avec la méthode `save()` et un id à chaque création d'objet.

Pour vérifier que l'objet a bien été créé, vous devez écrire dans le terminal : 
    
    - Afficher tous les objets `Question`

Maintenant que vous avez créé un objet, vous pouvez le récupérer dans la base de données.

## Récupérer un objet

Vous allez récuperer les objets suivants Question dans la base de données.

    - Récupérer un objet `Question` avec l'id 1
    - Récupérer un objet `Question` avec la question "What is the question"
    - Récupérer un objet `Question` avec la date d'aujourd'hui

## Modifier un objet

A présent, vous devez modifier un objet Question 
    
    - Modifier la question de l'objet `Question` avec la question "What is the question" par "What is your name ?"

## Supprimer un objet

A présent, vous devez supprimer un objet Question
    
    - Supprimer l'objet `Question` avec la question "What is your name ?"

En parralèle, vous pouvez vérifier en meme temps tous les changements que vous avez fait depuis l'interface d'administration en allant sur la page /admin de votre serveur.

# Step 7 : Creation de vues plus avancer


Pour créer une vue, vous devez écrire dans le fichier `polls/views.py` : 
    
    - Créer une vue qui renvoie la liste des questions publiées il y a moins d'un jour
    - Créer une vue qui renvoie les détails d'une question particulière
    - Créer une vue qui renvoie les résultats d'une question
