# Application de Gestion des Personnes (Fullstack REST + React)

## 📝 Description du projet
Ce projet est une application web Fullstack respectant l'architecture Client/Serveur. Il permet la gestion complète d'un annuaire de personnes (CRUD) à travers une interface moderne et réactive.

L'application est composée de deux parties distinctes :
1.  **Backend (API REST)** : Un serveur Java EE utilisant JAX-RS et Hibernate pour exposer des services web et interagir avec une base de données MySQL.
2.  **Frontend (Client Web)** : Une interface utilisateur développée avec React.js qui consomme les services REST pour afficher, ajouter, modifier et supprimer des données.

### Fonctionnalités principales :
* Listing de toutes les personnes.
* Ajout d'une nouvelle personne.
* Modification d'une personne existante (pré-remplissage des champs).
* Suppression d'une personne avec confirmation.
* Recherche dynamique par nom ou par ID.

---

## 🛠️ Technologies Utilisées

### Partie Backend (Serveur)
* **Langage :** Java (JEE)
* **Framework REST :** JAX-RS (Implémentation Jersey 2.x)
* **ORM (Persistance) :** JPA avec Hibernate 5.x
* **Base de données :** MySQL
* **Serveur d'application :** Apache Tomcat 9
* **Gestionnaire de dépendances :** Maven

### Partie Frontend (Client)
* **Framework :** React.js (v18+)
* **Build Tool :** Vite
* **Requêtes HTTP :** Axios
* **Routage :** React Router DOM
* **Design :** CSS3 (Custom + Responsive) & HeroIcons

---

## 🚀 Instructions pour exécuter le projet

Suivez ces étapes dans l'ordre pour lancer l'application localement.

### 1. Configuration de la Base de Données
1.  Assurez-vous que **MySQL** est lancé (via XAMPP, WAMP ou Workbench).
2.  Créez une base de données vide nommée `mytest`.
3.  *Note : La table `person` sera créée automatiquement par Hibernate lors du premier lancement.*
4.  Vérifiez le fichier `Backend/src/META-INF/persistence.xml` pour adapter l'utilisateur (`root`) et le mot de passe `root`.

### 2. Installation et Lancement du Backend
1.  Ouvrez **Eclipse IDE**.
2.  Importez le dossier `Backend` comme un **"Existing Maven Project"**.
3.  Faites un clic-droit sur le projet > **Maven** > **Update Project** (Force Update).
4.  Assurez-vous que les dépendances Maven sont bien déployées (Clic-droit > Properties > Deployment Assembly > Add > Maven Dependencies).
5.  Faites un clic-droit sur le projet > **Run As** > **Run on Server** (Tomcat v9).
6.  **Vérification :** Ouvrez votre navigateur sur `http://localhost:8080/Backend/rest/persons`. Vous devriez voir `[]` ou une liste JSON.

### 3. Installation et Lancement du Frontend
1.  Ouvrez un terminal (PowerShell ou CMD).
2.  Naviguez vers le dossier du frontend (là où se trouve `package.json`) :
    ```bash
    cd Frontend/REACT
    ```
3.  Installez les dépendances :
    ```bash
    npm install
    ```
4.  Lancez le serveur de développement :
    ```bash
    npm run dev
    ```
5.  Ouvrez l'URL indiquée dans le terminal (généralement `http://localhost:5173`) dans votre navigateur.

---

## 📸 Aperçu de l'API REST
Le backend expose les endpoints suivants via l'URL de base `http://localhost:8080/Backend/rest` :

| Méthode | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/persons` | Récupère la liste de toutes les personnes |
| `GET` | `/persons/{id}` | Récupère une personne par son ID |
| `GET` | `/persons/search?name={val}` | Recherche une personne par nom |
| `POST` | `/persons` | Ajoute une nouvelle personne (JSON body requis) |
| `PUT` | `/persons` | Met à jour une personne (JSON body avec ID requis) |
| `DELETE` | `/persons/{id}` | Supprime une personne par son ID |

Remarque (Difficultés rencontrées) : 
Erreur 404 au lancement du serveur. Lors du premier déploiement sur Tomcat, l'accès aux endpoints REST (/rest/persons) renvoyait une erreur 404 (Not Found), bien que le serveur soit démarré.

---

## 👤 Auteurs
* **[Mohamed Salah Zahouani + Mohamed Ghassen Zahouani / Groupe 1]**
* Projet réalisé dans le cadre du module "Services Web REST avec JPA".
