```mermaid

flowchart LR
    Admin((Administrateur))

    subgraph AdminUC[Cas d'usage Admin]
        UC12([Créer / Modifier / Supprimer une ressource])
        UC13([Gérer catégories / tags])
        UC14([Gérer utilisateurs])
        UC15([Consulter statistiques])
    end

    Admin --> UC12
    Admin --> UC13
    Admin --> UC14
    Admin --> UC15
