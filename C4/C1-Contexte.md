# Mon Architecture

Voici le diagramme de contexte du projet :

```mermaid
graph TD
    subgraph Utilisateurs
        direction TB
        C_NC["Citoyen non connecté<br/><small>Consultation libre</small>"]
        C_C["Citoyen connecté<br/><small>Création, partage</small>"]
        MOD["Modérateur<br/><small>Contrôle et validation</small>"]
        ADMIN["Administrateur<br/><small>Gestion du catalogue</small>"]
        S_ADMIN["Super Administrateur<br/><small>Gestion des admins</small>"]
    end

    subgraph SP [Systeme Principal]
        RSR["(RE)Sources Relationnelles<br/><small>Plateforme Web & Mobile</small>"]
    end

    subgraph SE [Systemes Externes]
        AUTH["Identité numérique<br/><small>Système d'authentification</small>"]
        API_STAT["API statistiques<br/><small>Bases externes</small>"]
    end

    %% Relations Utilisateurs vers Système
    C_NC -->|"Consultation<br/><small>HTTPS</small>"| RSR
    C_C -->|"Création / Partage<br/><small>HTTPS</small>"| RSR
    MOD -->|"Validation<br/><small>HTTPS</small>"| RSR
    ADMIN -->|"Gestion Catalogue<br/><small>HTTPS</small>"| RSR
    S_ADMIN -->|"Gestion Admins<br/><small>HTTPS</small>"| RSR

    %% Relations Système vers Externes
    RSR -.->|"Validation Token<br/><small>OIDC / OAuth2</small>"| AUTH
    RSR -->|"Envoi Données<br/><small>REST JSON</small>"| API_STAT

    %% Application des styles
    class C_NC,C_C user;
    class MOD,ADMIN,S_ADMIN staff;
    class RSR core;
    class AUTH,API_STAT external;

    %% Définitions des styles
    classDef user fill:#E0F2FE,stroke:#0284C7,stroke-width:1px;
    classDef staff fill:#FEF9C3,stroke:#F59E0B,stroke-width:1px;
    classDef core fill:#DCFCE7,stroke:#16A34A,stroke-width:1px;
    classDef external fill:#F1F5F9,stroke:#475569,stroke-width:1px;