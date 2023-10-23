![16654934257102_DW-P7-Back-end_company-banner](https://github.com/beseb/Vieux-Grimoire-Complet/assets/10258961/ba81748b-f852-4578-a7f7-9a0fd5c43df6)

# Vieux-Grimoire-Complet
Repo complet du Vieux Grimoire d'OpenClassrooms, un projet de site de notation de livres.
Fait avec React pour le frontend et NodeJS, ExpressJS et MongoDB pour le backend.


# Frontend
"npm install", puis "npm start" pour lancer le frontend.

# Backend 
"npm install", puis "nodemon server" pour lancer le backend. Vous aurez besoin d'un fichier .env pour accéder à la DB MongoDB.

# Spécifications de l'API

![spec1](https://github.com/beseb/Vieux-Grimoire-Complet/assets/10258961/d82bebbf-815b-4d8b-beef-d32744777fc2)
![spec2](https://github.com/beseb/Vieux-Grimoire-Complet/assets/10258961/bc044e36-a819-4b8a-878d-95d9dccd5a62)

# API Errors
Les erreurs éventuelles doivent être renvoyées telles qu'elles se sont produites, sans modification ni ajout. Si nécessaire, utilisez une nouvelle Error().

# API Routes
Toutes les routes pour les livres doivent disposer d’une autorisation (le token est envoyé par le front-end avec l'en-tête d’autorisation « Bearer »). Avant qu’un utilisateur puisse apporter des modifications à la route livre (book), le code doit vérifier si le user ID actuel correspond au user ID du livre. Si le user ID ne correspond pas, renvoyer « 403: unauthorized request ». Cela permet de s'assurer que seul le propriétaire d’un livre puisse apporter des modifications à celui-ci.

# Models
User {
email : String - adresse e-mail de l’utilisateur [unique]
password : String - mot de passe haché de l’utilisateur
}

Book {
userId : String - identifiant MongoDB unique de l'utilisateur qui a créé le livre
title : String - titre du livre
author : String - auteur du livre
imageUrl : String - illustration/couverture du livre
year: Number - année de publication du livre
genre: String - genre du livre
ratings : [
{
userId : String - identifiant MongoDB unique de l'utilisateur qui a noté le livre
grade : Number - note donnée à un livre
}
] - notes données à un livre
averageRating : Number - note moyenne du livre
}

# Sécurité
Le mot de passe de l'utilisateur doit être haché.
L'authentification doit être renforcée sur toutes les routes livre (book) requises.
Les adresses électroniques dans la base de données sont uniques, et un plugin Mongoose approprié est utilisé pour garantir leur unicité et signaler les erreurs.
La sécurité de la base de données MongoDB (à partir d'un service tel que MongoDB Atlas) ne doit pas empêcher l'application de se lancer sur la machine d'un utilisateur.
Les erreurs issues de la base de données doivent être remontées.


