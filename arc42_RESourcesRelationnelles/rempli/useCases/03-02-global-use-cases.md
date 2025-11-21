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
        
        UC1([Consulter catalogue])
        UC2([Consulter une ressource])
        UC3([Créer un compte])
        UC4([Se connecter])
        UC5([Commenter une ressource])
        UC6([Signaler un contenu])
        UC7([Ajouter aux favoris])
        UC8([Partager une ressource])
        UC9([Suivre sa progression])
        UC10([Se déconnecter])
        
        UC11([Consulter contenus signalés])
        UC12([Supprimer un commentaire])
        UC13([Supprimer une ressource])

        UC14([Créer / Modifier / Supprimer une ressource])
        UC15([Gérer catégories / tags])
        UC16([Gérer utilisateurs])
        UC17([Consulter statistiques])

        UC18([Gérer rôles et permissions])
        UC19([Configurer les paramètres système])
        UC20([Audit & conformité RGPD])
    end

    %% Liens Citoyens
    Citizen --> UC1
    Citizen --> UC2
    Citizen --> UC3

    CitizenConnected --> UC4
    CitizenConnected --> UC5
    CitizenConnected --> UC6
    CitizenConnected --> UC7
    CitizenConnected --> UC8
    CitizenConnected --> UC9
    CitizenConnected --> UC10

    %% Liens Modérateurs
    Moderator --> UC11
    Moderator --> UC12
    Moderator --> UC13

    %% Liens Administrateurs
    Admin --> UC14
    Admin --> UC15
    Admin --> UC16
    Admin --> UC17

    %% Liens Super-admin
    SuperAdmin --> UC18
    SuperAdmin --> UC19
    SuperAdmin --> UC20

