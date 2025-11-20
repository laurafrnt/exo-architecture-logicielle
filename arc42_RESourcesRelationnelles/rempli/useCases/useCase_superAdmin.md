```mermaid
flowchart LR
    SuperAdmin((Super-Administrateur))

    subgraph SuperAdminUC[Cas d'usage Super Admin]
        UC16([Gérer rôles et permissions])
        UC17([Configurer les paramètres système])
        UC18([Audit & conformité RGPD])
    end

    SuperAdmin --> UC16
    SuperAdmin --> UC17
    SuperAdmin --> UC18
