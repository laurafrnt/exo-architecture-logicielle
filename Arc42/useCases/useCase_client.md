```mermaid
flowchart LR
    Citizen((Citoyen))
    CitizenConnected((Citoyen connecté))

    subgraph CitizenUC[Cas d'usage Citoyen]
        UC1([Consulter catalogue])
        UC3([Consulter une ressource])
        UC2([Créer un compte / Se connecter])
        UC4([Commenter une ressource])
        UC5([Signaler un contenu])
        UC6([Ajouter aux favoris])
        UC7([Partager une ressource])
        UC8([Suivre sa progression])
    end

    Citizen --> UC1
    Citizen --> UC3

    CitizenConnected --> UC2
    CitizenConnected --> UC4
    CitizenConnected --> UC5
    CitizenConnected --> UC6
    CitizenConnected --> UC7
    CitizenConnected --> UC8
