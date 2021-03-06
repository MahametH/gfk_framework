# Description

Cours de Grafikart pour la création d'un Framework modulaire en PHP

# Cours

1. [Structure du projet](https://youtu.be/WHjx-MfgaFo):

    * Présentation de l'architecture du projet
    * Mise en place des outils nécessaire au projet  
        * Composer : Outils pour créer un autoload et gérer les dépendances
        * Git : Outils pour le versionning
        * [PHPUnit](https://packagist.org/packages/phpunit/phpunit): Outils pour faire des tests unitaires
        * [guzzlehttp/psr7](https://packagist.org/packages/guzzlehttp/psr7): Classes qui implémente le PSR-7 pour gérer les $requests et les $responses
        * [http-interop/response-sender](https://packagist.org/packages/http-interop/response-sender): Classes qui gère les $responses de type PSR-7 pour les envoyer au serveur
        * [squizlabs/php_codesniffer](https://packagist.org/packages/squizlabs/php_codesniffer): Outils de test pour vérifier si le code respecte le PSR-2

2. [Le router](https://youtu.be/-iW6lo6wq1Y):

    * Création d'un Router pour gérer la lecture des URL et la création des Routes
    * Création des Routes pour gérer le lien entre l'URL et la Response
    * Utilisation des regex pour trouver les routes (test :[regex](https://regex101.com/))
    * Utilisation de nouveaux outils :
        * [zendframework/zend-expressive-fastroute](https://packagist.org/packages/zendframework/zend-expressive-fastroute): Router qui implémente [nikic/fast-route](https://packagist.org/packages/nikic/fast-route)

3. [Le renderer](https://youtu.be/lP5Jy2tI_7Q):

    * Intégration des vues grâce au Renderer et au Router.
    * Création d'un système qui récupère le "slug" de l'URI pour le passer à la vue
    * Création d'un pseudo système de templates
    
4. [Twig](https://youtu.be/A9K--97_pbU):

    * Modification des vues et du template pour qu'ils s'affichent à partir du moteur de template Twig
    * Utilisation de nouveaux outils :
        * [twig/twig](https://packagist.org/packages/twig/twig)
        
5. [Conteneur de dépendance](https://youtu.be/JuB90IYXOwU):

    * Ajout d'un container de dépendances
    * Refactoring des classes pour permettre de mieux gérer les dépendances
    * Création des deux fichiers de config pour gérer le container de dépendance
    * Séparation entre BlogAction et BlogModule pour que le Module ne gère plus les appels
    * Création d'un TwigRendererFactory pour gérer la création du TwigRenderer
    * Utilisation de nouveaux outils :
        * [php-di/php-di](https://packagist.org/packages/php-di/php-di)
        
6. [Les migrations](https://youtu.be/U_6NhMbl9ZA):

    * Création d'un module de migration avec PHINX, permet de :
         * Gérer la création, modification et suppression des tables avec des classes PHP
         * Utilise un fichier de configuration PHP pour gérer les tables et le contenu
         * Lors du passage de la BDD en local, vers la BDD en ligne, les BDD seront identiques grâce aux classes PHP
    * Utilisation de nouveaux outils :
        * [robmorgan/phinx](https://packagist.org/packages/robmorgan/phinx) qui permet la gestion des migrations
        * [fzaninotto/faker](https://packagist.org/packages/fzaninotto/faker) pour remplir une BDD de fausses données
        
7. [Récupération des articles](https://youtu.be/MM1KswRD7TE):

    * Création d'une connexion à la base de données
    * Création d'objets "Table" qui seront les modèles de l'application
    * Séparation du code avec les objets "Actions" qui sont les controlleurs de l'application
    * Modification des vues pour qu'elles arrivent à lire les données reçues maintenant
    
8. [Pagination](https://youtu.be/lbNjgtB2e_I):

    * Création d'un module pour gérer la pagination des posts
    * Installation de pagerfanta qui va automatiquement :
        * récupérer le nombre d'article nécessaire
        * créer la barre de navigation pour passer d'une page à l'autre
    * Création d'une Entity pour stocker les posts
    * Gestion des DateTime grâve à timeago.js pour afficher différement les dates 
    * Utilisation de nouveaux outils :
         * [pagerfanta/pagerfanta](https://packagist.org/packages/pagerfanta/pagerfanta) créé une pagination automatique avec gestion des pages
         * [timeago.js](https://cdnjs.com/libraries/timeago.js) pour modifier l'affichage des dates en "il y a X temps"