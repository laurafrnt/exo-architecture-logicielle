# Mon Architecture

Voici le diagramme de contexte du projet :

```mermaid
C4Container
title (RE)Sources Relationnelles – Diagramme de Conteneurs (C2)

Person(user_citizen, "Citoyen", "Utilise la plateforme pour accéder aux ressources.")
Person(user_admin, "Administrateur / Modérateur", "Gère et modère le contenu.")

System_Boundary(sys, "(RE)Sources Relationnelles") {

  Container(mobile_app, "App Mobile", "Android / iOS", "Application mobile hybride en HTML5/JS permettant l’accès citoyen au front-office.")
  Container(web_front, "Application Web Front-Office", "HTML5 / CSS3 / JS", "Interface web pour les citoyens.")
  Container(web_back, "Application Web Back-Office", "HTML5 / CSS3 / JS", "Interface web d’administration et de modération.")
  
  Container(api_backend, "API Backend", "MVC / REST", "Expose les services métier, gère la logique applicative et la sécurité (RGPD).")
  
  ContainerDb(database, "Base de Données Relationnelle", "PostgreSQL / MySQL", "Stocke les ressources, utilisateurs, permissions, logs.")
}

System_Ext(auth_ext, "Système d’Authentification Externe", "OAuth2 / SSO", "Permet l’authentification sécurisée.")

Rel(user_citizen, mobile_app, "Utilise", "HTTPS")
Rel(user_citizen, web_front, "Accède à", "HTTPS")
Rel(user_admin, web_back, "Administre via", "HTTPS")

Rel(mobile_app, api_backend, "Appels REST", "HTTPS")
Rel(web_front, api_backend, "Appels REST", "HTTPS")
Rel(web_back, api_backend, "Appels REST", "HTTPS")

Rel(api_backend, database, "Lecture / Écriture SQL", "JDBC / ORM")

Rel(api_backend, auth_ext, "Vérification identité", "OAuth2 / SSO")
