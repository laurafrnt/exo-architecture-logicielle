# 🧩 ConversionRequest – Prompt 3

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ConversionRequest>
  <Meta>
    <Role>Architecte logiciel</Role>
    <Action>Convertir le prompt en XML</Action>
    <Date></Date>
  </Meta>

  <Example>
    <Title>2.3 Exemple</Title>
    <Table>
      <Row>
        <PartiePrenante>Utilisateur final</PartiePrenante>
        <Preoccupation>Performance, disponibilité</Preoccupation>
        <PointDeVue>Vue d’usage (Use Case)</PointDeVue>
      </Row>
      <Row>
        <PartiePrenante>DSI</PartiePrenante>
        <Preoccupation>Coût, maintenance</Preoccupation>
        <PointDeVue>Vue déploiement</PointDeVue>
      </Row>
      <Row>
        <PartiePrenante>RSSI</PartiePrenante>
        <Preoccupation>Sécurité, conformité</Preoccupation>
        <PointDeVue>Vue sécurité (STRIDE, ASVS)</PointDeVue>
      </Row>
      <Row>
        <PartiePrenante>Développeur</PartiePrenante>
        <Preoccupation>Cohérence du code</Preoccupation>
        <PointDeVue>Vue composant / package</PointDeVue>
      </Row>
      <Row>
        <PartiePrenante>Exploitant</PartiePrenante>
        <Preoccupation>Monitoring, logs</Preoccupation>
        <PointDeVue>Vue runtime / infra</PointDeVue>
      </Row>
    </Table>
  </Example>

  <Project>
    <Titre>(RE)SOURCES RELATIONNELLES</Titre>
    <Resume>Le projet « (RE)Sources Relationnelles » est une simulation d’un projet qui pourrait être porté par le Ministère des Solidarités et de la Santé à destination des citoyens afin de proposer une plateforme de sources, ressources, et d’échanges.</Resume>
    <Disclaimer>Le sujet a été intégralement conçu à partir de cette idée, les documents fournis ne sont donc pas officiels et n’émergent pas du Ministère des Solidarités et de la Santé. Certains documents de présentation du Ministère contiennent néanmoins des informations réelles issues des sites Ministériels.</Disclaimer>
    <Organisation>Chaque groupe sera désigné dans le présent document comme « le prestataire ».</Organisation>
    <Orientation>L’accent sera mis sur les qualités techniques et économiques des projets mais également sur les aspects organisationnels et humains, à travers l’acquisition ou l’ancrage de softs skills.</Orientation>

    <EnjeuxPrincipaux>
      <But>Proposer des ressources et outils pour créer, renforcer et enrichir les relations des citoyens.</But>
      <Contexte>Selon la pyramide de Maslow, les besoins humains se structurent par priorités — sécurité, sens, développement personnel, accomplissement — et la qualité des relations est un levier majeur.</Contexte>
      <Cible>Parents, couple, famille, amis, collègues — chaque type de relation nécessite des lignes de communication adaptées.</Cible>
      <ObjectifPrincipal>Proposer une plateforme autour de la qualité des liens relationnels pour une meilleure qualité de vie.</ObjectifPrincipal>
    </EnjeuxPrincipaux>

    <Objectifs>
      <Objectif> Mise à disposition de ressources de différents types pour les usagers </Objectif>
      <Objectif> Mise en place d’un outil de gestion du catalogue de ressources (catégories, types de relations concernées, types de ressources, etc.) </Objectif>
      <Objectif> Donner la possibilité de créer et partager des ressources </Objectif>
      <Objectif> Permettre l’édition de statistiques en rapports aux ressources à disposition (consultations, recherches, partages) </Objectif>
    </Objectifs>
  </Project>

  <Request>
    <Description>Générer un tableau reprenant l'exemple fourni afin de définir les parties prenantes pour le projet ci-dessus.</Description>
    <OutputFormat>XML</OutputFormat>
  </Request>
</ConversionRequest>
```

