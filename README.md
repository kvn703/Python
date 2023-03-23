# Workshop: Python 


Python est un langage de programmation largement utilisé dans les applications Web, le développement de logiciels, la science des données et le machine learning (ML). Les développeurs utilisent Python parce que c'est un langage efficace et facile à apprendre, et qu'il peut s'exécuter sur de nombreuses plateformes différentes. C'est pour cela on vous propose de découvrir ce langage de programmation à travers ce workshop.


 # Partie 1 : Initiation à Python
 
   ## Task 00 -HelloWord :
    Créer un fichier Task00.py qui fonction une fonction hello_world() qui
    affiche "Hello World" lors de l'éxécution.
    
   ##
   ```Output : "Hello World"```
    
   ## Task 01 - Variables :
    
    Maintenant, reprendre votre function hello_world et modifier-la de sorte qu'il prenne en paramètre un string NAME et affiche "Hello World + NAME" 

   ##
   ```Example : name = "Josué"  = ```
   ```Output : "Hello World Josué" ```

   ## Task 02 - Arithmetique :
    Réaliser les 4 fonctions suivante :
        - addition(A, B) qui fait l'addition de A et B
        - soustraction(A, B) qui fait la soustraction de A et B
        - multiplication(A, B) qui fait la multiplication de A et B
        - division(A, B) qui fait la division de A et B
        - modulo(A, B) qui fait le modulo de A et B
    Ces fonctions doivent retourner le résultat de l'opération. Attention, il faut gérer les erreurs. 
    Si B est égal à 0, la fonction doit retourner "Error: division by zero"

##
   ```Example1 : soustraction(1, 2) = ```
   ```Output : -1 ```
##
   ```Example2 : division(1, 0) = ```
   ```Output : "Error: division by zero" ```

## Task 03 - Boucles :
     En python, il existe 2 types de boucles : while et for.
    
    Choisissez une des deux boucles et réaliser les 3 fonctions suivantes :ù
        - alphabet() qui affiche l'alphabet en majuscule
        - numbers(n) qui affiche les nombres de 0 à n
        - sum(n) qui fait la somme des nombres de 1 à n (boucle for ou while)
        - factorial(n) qui fait la factorielle de n (boucle for ou while)
        - power(n, p) qui fait la puissance de n à la puissance p (boucle for ou while)
        
   ##
   ```Example : alphabet() = ```
   ```Output : "ABCDEFGHIJKLMNOPQRSTUVWXYZ" ```
##
   ```Example : numbers(5) = ```
   ```Output : 012345 ```
   ##
   ```Example : sum(5) = ```
   ```Output : 15```
   ##
   ```Example : factorial(5) = ```
   ```Output : 120```
   ##
   ```Example : power(5, 3) = ```
   ```Output : 125```


##
   
   ## Task 04 -list :
      Maintenant, découvrons c'est quoi une liste en Python. Une liste est une collection ordonnée et modifiable.
      Par exemple, voici une liste de fruits en python:  fruits = ["apple", "banana", "cherry"]
      Créer les fonctions suivantes qui :
##

      STEP 1 : Crée une liste de 5 fruits et affiche la liste. 
      fruits = ["apple", "banana", "cherry", "orange", "kiwi"])

   ```Output : ["apple", "banana", "cherry", "orange", "kiwi"])```
##
      STEP 2 : Ajoute un fruit "ananas" à la liste et affiche la liste.
   ```Output : ["ananas", "apple", "banana", "cherry", "orange", "kiwi"]```
##
      STEP 3 : Supprime le fruit "banana" de la liste et affiche la liste.
   ```Output : ["ananas", "apple", "cherry", "orange", "kiwi"]```
##
      STEP 5 : Affiche le dernier élément de la liste.
   ```output = "kiwi"```
##
      STEP 6 : Affiche le nombre d'éléments de la liste.
   ```output = 5```
##
      STEP 7 : Cherche un élément dans la liste et affiche la position de l'élément.
   ```Example : fruit = "orange" = ```
   ```Output : 3```
##   

## Task 05 - Dictionaires :
        Maintenant, découvrons c'est quoi un dictionaire en Python. Un dictionaire est une collection non ordonnée et modifiable.
        Par exemple, voici un dictionaire de fruits et le nombre de fruits disponible en python:  fruits = {"apple": 5, "banana": 5, "cherry": 5}
        Créer les fonctions suivantes qui :
##
        STEP 1 : Crée un dictionaire de 5 fruits et affiche le dictionaire.
   ```Output :  {"apple": 5, "banana": 5, "cherry": 5, "orange": 5, "kiwi": 5} ```
##
        Step 2 : Ajoute un fruit "ananas" à la liste et affiche le dictionaire.
   ```Output :  {"ananas": 5, "apple": 5, "banana": 5, "cherry": 5, "orange": 5, "kiwi": 5} ```
##
        Step 3 : Supprime une unité du fruit "banana" de la liste et affiche le dictionaire.
   ```Output :  {"ananas": 5, "apple": 5, "banana": 4, "cherry": 5, "orange": 5, "kiwi": 5} ```
##
        Step 4 : Affiche SEULEMENT le nombre de fruit "banana" qui reste.
   ```Output : 4```
##

## Task 06 - Random :
    Maintenant, découvrons c'est quoi un random en Python. Un random est une fonction qui permet de générer un nombre aléatoire.
    Créer les fonctions suivantes qui :
##
    STEP 1 : Crée une fonction qui génère un nombre aléatoire entre 0 et 100 et affiche le nombre.
   ```Output : (un nombre aléatoire entre 0 et 100)```
##
     STEP 2 : Crée une fonction qui génére un nombre aléatoire et affiche "Pair" si le nombre est pair et "Impair" si le nombre est impair.

# Partie 2: The Project
  
   ## Jeu de Lotterie :
    Créer un jeu de lotterie qui demande à l'utilisateur de choisir 6 nombres entre 1 et 49.

    Le programme doit générer 6 nombres aléatoires entre 1 et 49 et afficher les 6 nombres choisis par l'utilisateur et les 6 nombres générés par le programme.

    Le programme doit ensuite afficher le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 6, le programme doit afficher "Bravo, vous avez gagné le jackpot !" et additionne le double de sa victoire à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 5, le programme doit afficher "Bravo, vous avez gagné 1000$ !" et additione 1000$ à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 4, le programme doit afficher "Bravo, vous avez gagné 100$ !" et additione 100$ à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 3, le programme doit afficher "Bravo, vous avez gagné 10$ !" et additione 10$ à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 2, le programme doit afficher "Bravo, vous avez gagné 1$ !" et additione 1$ à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 1, le programme doit afficher "Bravo, vous avez gagné 0.5$ !" et additione 0.5$ à son gain.

    Si le nombre de nombres choisis par l'utilisateur qui sont présents dans les nombres générés par le programme est égal à 0, le programme doit afficher "Désolé, vous n'avez rien gagné !" et ne change pas son gain.

    Chaque fois que le joueur joue au jeux, cela lui coutera 5$.
    Au début du programme le joueur a par défaut 20$.
    A chaque tour, le joueur a le choix de jouer ou de quitter le jeu.
    S'il ne veut pas jouer, le programme doit afficher le gain total du joueur et le quitter.
    S'il n'a pas assez d'argent pour jouer, le programme doit afficher "Vous n'avez plus assez d'argent pour jouer !" et le quitter.

## josue.nanthakumar@epitech.eu / kevin.nadarajah@epitech.eu