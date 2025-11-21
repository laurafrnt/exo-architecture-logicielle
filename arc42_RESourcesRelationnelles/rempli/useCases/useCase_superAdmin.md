```mermaid
flowchart LR
    SuperAdmin((Super-Administrateur))

    subgraph SuperAdminUC[Cas d'usage Super Admin]
        UC18([Gérer rôles et permissions])
        UC19([Configurer les paramètres système])
        UC20([Audit & conformité RGPD])
    end

    SuperAdmin --> UC18
    SuperAdmin --> UC19
    SuperAdmin --> UC20
