# Mon Architecture

Voici le diagramme de contexte du projet :

```mermaid
graph TD
  %% --------- Groupes visuels ----------
  subgraph Utilisateurs
    citoyen_visiteur["Citoyen non connecté<br/><small>Utilisateur anonyme consultant le contenu public.</small>"]
    citoyen_membre["Citoyen connecté<br/><small>Utilisateur authentifié pouvant créer et partager des ressources.</small>"]
    moderateur["Modérateur<br/><small>Chargé du contrôle et de la validation des contenus.</small>"]
    admin["Administrateur<br/><small>Responsable de la gestion globale de la plateforme.</small>"]
  end

  subgraph SystemePrincipal["(RE)Sources Relationnelles<br/><small>Plateforme web et mobile favorisant la cohésion sociale.</small>"]
    systeme_re["Système (RE)Sources Relationnelles"]
  end

  subgraph SystemesExternes["Systèmes externes"]
    api_stats["API Statistiques<br/><small>Bases de données externes pour l'analyse statistique.</small>"]
    auth_system["Identité Numérique<br/><small>Système d'authentification tiers.</small>"]
  end

  %% --------- Relations ----------
  citoyen_visiteur -->|"Consulte les ressources (lecture seule)<br/><small>HTTPS</small>"| systeme_re
  citoyen_membre -->|"Crée, partage et consulte du contenu<br/><small>HTTPS</small>"| systeme_re

  moderateur -->|"Valide les publications<br/><small>HTTPS</small>"| systeme_re
  admin -->|"Configure et gère le système<br/><small>HTTPS</small>"| systeme_re

  systeme_re -->|"Envoie les données d'usage<br/><small>API REST/JSON</small>"| api_stats
  systeme_re -->|"Délègue l'authentification<br/><small>OIDC / OAuth2</small>"| auth_system

  %% --------- Styles ----------
  classDef user fill:#E0F2FE,stroke:#0284C7,stroke-width:1px;
  classDef staff fill:#FEF9C3,stroke:#F59E0B,stroke-width:1px;
  classDef core fill:#DCFCE7,stroke:#16A34A,stroke-width:1px;
  classDef external fill:#F1F5F9,stroke:#475569,stroke-width:1px;

  class citoyen_visiteur,citoyen_membre user;
  class moderateur,admin staff;
  class systeme_re core;
  class api_stats,auth_system external;
