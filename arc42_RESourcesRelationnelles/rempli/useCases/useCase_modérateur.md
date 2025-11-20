```mermaid
flowchart LR
    Moderator((Modérateur))

    subgraph ModUC[Cas d'usage Modération]
        UC9([Consulter contenus signalés])
        UC10([Valider / Refuser un commentaire])
        UC11([Bannir temporairement un utilisateur])
    end

    Moderator --> UC9
    Moderator --> UC10
    Moderator --> UC11
