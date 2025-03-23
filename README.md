 PROJETUVCI 

 1. Description  
PROJETUVCI est une application web développée en PHP permettant de gérer divers services. Elle est organisée en plusieurs dossiers pour une meilleure structure et maintenabilité du code.  

 2. Installation et Hébergement sur un Serveur Local  

 Étape 1 : Décompresser et Déplacer le Projet  

1. Télécharger le fichier PROJETUVCI.zip.  
2. Décompresser le fichier PROJETUVCI.zip sur votre ordinateur.  
3. Déplacer le dossier PROJETUVCI dans le répertoire correspondant à votre serveur local :  
   - WAMP : `C:\wamp64\www\PROJETUVCI\`  
     

 Étape 2 : Démarrer le Serveur Local  

1. Ouvrir WAMP ou XAMPP.  
2. Démarrer les services Apache et MySQL.  

 Étape 3 : Configurer la Base de Données  

 1. Accéder à phpMyAdmin  
- Ouvrir un navigateur web et taper l'URL suivante :  
  - WAMP : http://localhost/phpmyadmin  
  - XAMPP : http://localhost/phpmyadmin 

 2. Créer une nouvelle base de données  
1. Dans phpMyAdmin, cliquer sur Bases de données.  
2. Dans le champ Nom de la base de données, saisir : `PROJETUVCI`.  
3. Sélectionner l'encodage utf8_general_ci (optionnel, mais recommandé).  
4. Cliquer sur Créer.  

 3. Importer le fichier SQL  

1. Aller dans l'onglet Importer.  
2. Cliquer sur Choisir un fichier.  
3. Sélectionner le fichier `PROJETUVCI.sql` qui se trouve dans le dossier du projet.  
4. Cliquer sur Exécuter pour importer les tables et les données.  

 Étape 4 : Configuration de la Connexion à la Base de Données  
1. Ouvrir le fichier config/config.php avec un éditeur de texte (Notepad++, VS Code, Sublime Text, etc.).  
2. Vérifier et modifier si nécessaire les paramètres de connexion :  
  
 <?php
// Paramètres de connexion à la base de données
$servername = "localhost";  // L'adresse du serveur MySQL
$username = "root";         // Nom d'utilisateur MySQL (en local, c'est souvent 'root')
$password = "";             // Mot de passe MySQL (vide en local si tu n'as pas défini de mot de passe)
$dbname = "PROJETUVCI"; // Nom de ta base de données

// Création de la connexion à la base de données
$mysqli = new mysqli($servername, $username, $password, $dbname);

// Vérification de la connexion
if ($mysqli->connect_error) {
    die("Erreur de connexion : " . $mysqli->connect_error);  // Si la connexion échoue, afficher l'erreur
}

// Optionnel : définir le jeu de caractères pour éviter des problèmes d'encodage
$mysqli->set_charset("utf8");

  
3. Enregistrer et fermer le fichier.  

 Étape 5 : Accéder à l’Application  
1. Ouvrir un navigateur web.  
2. Entrer l’URL suivante :  
   - WAMP :localhost/PROJETUVCI/

3. L’application devrait maintenant s’afficher correctement.  


4. Structure du Projet  

Le projet est organisé comme suit :  

expressservice/
│── config/
│   ├── config.php       Fichier de connexion à la base de données
│
│── view/
│   ├── accueil.php         Page de presentation du projet
│   ├── connexion.php       Page de connexion utilisateur
│   ├── enregistrer.php     page de traitement des informations clients
│   ├── formulaire.php      page d'enregistrement de l'utilisateur 
│   ├── deconnexion.php     page de deconnexion
│   ├── layout/
│       ├── 		            Fichier contenant le menu de navigation du site
│
│── public/ 
│   ├── assets/               Contient les images, CSS et scripts JS (si existants)
│
│── index.php                  Page d'accueil principale
│── PROJETUVCI.sql          	Fichier SQL pour la base de données

 📂 Détails des Dossiers et Fichiers :  
- `config/config.php` → Permet d’établir la connexion entre l’application et la base de données.  
- `view/` → Contient les différentes pages de l’application :  
  - `accueil.php` : Présentation de l’entreprise.  
  - `connexion.php` : affiche la page de connexion pour l'utilisateur .  
  - `deconnexion.php` : affiche la page de deconnexion pour l'utilisateur .  
  - `enregistrer.php` : affiche la page de traitement de données 
  - `formulaire.php` : affiche la page de creaction de compte  
- `view/layout/` → Gère le menu de navigation inclus dans chaque page.  
- `public/` → Dossier prévu pour stocker les fichiers statiques (images, CSS, JavaScript).  
- `index.php` → Page d'accueil principale du site.  
- `PROJETUVCI.sql` → Fichier permettant d'importer la base de données.  

 5. Dépannage  

 🔹 Erreur de connexion à la base de données ?  
- Vérifier que MySQL est bien démarré.  
- Vérifier les paramètres dans `config/config.php` (nom de la base, utilisateur, mot de passe).  
- S'assurer que la base de données PROJETUVCI a bien été créée et importée.  
