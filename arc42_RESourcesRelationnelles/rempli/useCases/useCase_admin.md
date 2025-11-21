```mermaid

flowchart LR
    Admin((Administrateur))

    subgraph AdminUC[Cas d'usage Admin]
        UC14([Créer / Modifier / Supprimer une ressource])
        UC15([Gérer catégories / tags])
        UC16([Gérer utilisateurs])
        UC17([Consulter statistiques])
    end

    Admin --> UC14
    Admin --> UC15
    Admin --> UC16
    Admin --> UC17
