```mermaid
flowchart LR
    Citizen((Citoyen))
    CitizenConnected((Citoyen connecté))

    subgraph CitizenUC[Cas d'usage Citoyen]
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
    end

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