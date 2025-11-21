```mermaid
flowchart LR
    Moderator((Modérateur))

    subgraph ModUC[Cas d'usage Modération]
        UC11([Consulter contenus signalés])
        UC12([Supprimer un commentaire])
        UC13([Supprimer une ressource])
    end

    Moderator --> UC11
    Moderator --> UC12
    Moderator --> UC13