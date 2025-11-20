```mermaid
flowchart LR
    %% Acteurs
    Citizen((Citoyen))
    CitizenConnected((Citoyen connecté))
    Moderator((Modérateur))
    Admin((Administrateur))
    SuperAdmin((Super-Administrateur))

    %% Systèmes
    subgraph System[Plateforme RESources Relationnelles]
        
        UC1([UC1: Consulter le catalogue])
        UC2([UC2: Créer un compte / Se connecter])
        UC3([UC3: Consulter une ressource])
        UC4([UC4: Commenter une ressource])
        UC5([UC5: Signaler un contenu])
        UC6([UC6: Ajouter aux favoris])
        UC7([UC7: Partager une ressource])
        UC8([UC8: Suivre sa progression])
        
        UC9([UC9: Consulter contenus signalés])
        UC10([UC10: Valider / Refuser un commentaire])
        UC11([UC11: Bannir temporairement un utilisateur])

        UC12([UC12: CRUD Ressources])
        UC13([UC13: Gérer catégories / tags])
        UC14([UC14: Gérer utilisateurs])
        UC15([UC15: Consulter statistiques])

        UC16([UC16: Gérer rôles et permissions])
        UC17([UC17: Configurer paramètres système])
        UC18([UC18: Audit RGPD])
    end

    %% Liens Citoyens
    Citizen --> UC1
    Citizen --> UC3
    CitizenConnected --> UC2
    CitizenConnected --> UC4
    CitizenConnected --> UC5
    CitizenConnected --> UC6
    CitizenConnected --> UC7
    CitizenConnected --> UC8

    %% Liens Modérateurs
    Moderator --> UC9
    Moderator --> UC10
    Moderator --> UC11

    %% Liens Administrateurs
    Admin --> UC12
    Admin --> UC13
    Admin --> UC14
    Admin --> UC15

    %% Liens Super-admin
    SuperAdmin --> UC16
    SuperAdmin --> UC17
    SuperAdmin --> UC18

