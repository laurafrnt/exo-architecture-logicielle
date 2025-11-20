# Mon Architecture

Voici le diagramme de contexte du projet :

```mermaid
%% C1 + C2 combiné
%% Utilisation du style de C1 + ajout du C2 en syntaxe C4Container

flowchart TD

    %% --- Acteurs (inchangés) ---
    subgraph Utilisateurs
        direction TB
        C_NC["Citoyen non connecté<br/><small>Consultation libre</small>"]
        C_C["Citoyen connecté<br/><small>Création, partage</small>"]
        MOD["Modérateur<br/><small>Contrôle et validation</small>"]
        ADMIN["Administrateur<br/><small>Gestion du catalogue</small>"]
        S_ADMIN["Super Administrateur<br/><small>Gestion des admins</small>"]
    end

    %% --- Système Principal + C2 ---
    subgraph "Systeme Principal"
        direction TB

        RSR["(RE)Sources Relationnelles<br/><small>Plateforme Web & Mobile</small>"]

        subgraph C2["Détail interne (C2) - Conteneurs"]
            direction TB

            AppMobile["
                Container: App Mobile<br/>
                <small>Android / iOS<br/>HTML5 / JS (Hybrid)</small>
            "]

            WebFront["
                Container: Application Web Front-Office<br/>
                <small>HTML5, CSS3, JS</small>
            "]

            WebBack["
                Container: Application Web Back-Office<br/>
                <small>HTML5, CSS3, JS</small>
            "]

            API["
                Container: API Backend<br/>
                <small>MVC, REST JSON<br/>Contrôleurs, Services, Modèle</small>
            "]

            DB["
                ContainerDb: Base de Données SQL<br/>
                <small>PostgreSQL / MySQL</small>
            "]
        end
    end

    %% --- Systèmes Externes (inchangés) ---
    subgraph "Systemes Externes"
        API_STAT["API statistiques<br/><small>Bases externes</small>"]
        AUTH["Identité numérique<br/><small>OIDC / OAuth2</small>"]
    end

    %% --- Flux Utilisateurs (C1) ---
    C_NC -->|"Consulte<br/><small>HTTPS/JSON</small>"| RSR
    C_C -->|"Crée / Partage<br/><small>HTTPS/JSON</small>"| RSR
    MOD -->|"Contrôle<br/><small>HTTPS/JSON</small>"| RSR
    ADMIN -->|"Gère catalogue<br/><small>HTTPS/JSON</small>"| RSR
    S_ADMIN -->|"Gère admins<br/><small>HTTPS/JSON</small>"| RSR

    %% --- Flux internes (C2) ---
    RSR --> AppMobile
    RSR --> WebFront
    RSR --> WebBack

    AppMobile -->|"API REST"| API
    WebFront -->|"API REST"| API
    WebBack -->|"API REST"| API

    API -->|"Read/Write SQL"| DB

    %% --- Flux externes (C1) ---
    RSR -->|"Envoi statistiques<br/><small>REST JSON</small>"| API_STAT
    RSR -.->|"Authentification<br/><small>OIDC / OAuth2</small>"| AUTH

    %% Styles
    class C_NC,C_C user;
    class MOD,ADMIN,S_ADMIN staff;
    class RSR core;
    class API_STAT,AUTH external;

    classDef user fill:#E0F2FE,stroke:#0284C7,stroke-width:1px;
    classDef staff fill:#FEF9C3,stroke:#F59E0B,stroke-width:1px;
    classDef core fill:#DCFCE7,stroke:#16A34A,stroke-width:1px;
    classDef external fill:#F1F5F9,stroke:#475569,stroke-width:1px;
