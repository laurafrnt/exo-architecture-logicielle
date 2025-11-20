# 🎯 Use Cases — (RE)Sources Relationnelles

## 1. Acteurs

* **Citoyen non connecté**
  Consulte le catalogue, recherche des ressources, lit les commentaires publics.
* **Citoyen connecté**
  Participer : commenter, favoriser, partager, suivre sa progression.
* **Modérateur**
  Valide/retire contenus, gère signalements.
* **Administrateur**
  Gère catalogue, utilisateurs, statistiques générales.
* **Super-administrateur**
  Gère la configuration globale & droits avancés.

---

# 2. Cas d’usage — Citoyen (non connecté & connecté)

### UC1 — **Consulter le catalogue de ressources**

* **Acteur** : Citoyen (non connecté ou connecté)
* **Objectif** : Parcourir les ressources publiques.
* **Scénario** :

  1. L’utilisateur accède à la page catalogue.
  2. Le système affiche les catégories, tags ou filtres.
  3. L’utilisateur consulte une fiche ressource.
* **Variantes** :

  * Recherche textuelle.
  * Filtres (thèmes, durée, public cible…).
* **Contraintes** :

  * RGAA : navigation clavier, alternatives textuelles.
  * RGPD : aucune donnée personnelle stockée si non connecté.

---

### UC2 — **Créer un compte / Se connecter**

* **Acteur** : Citoyen
* **Objectif** : Accéder aux fonctionnalités sociales et gamification.
* **Scénario** :

  1. L’utilisateur clique “Créer un compte / Connexion”.
  2. Saisie email + mot de passe ou social login.
  3. Validation RGPD (consentement explicite).
  4. Le système crée le compte / délivre un token.
* **Post-condition** : Identité stockée, profil minimal créé.

---

### UC3 — **Consulter une ressource en détail**

* **Acteur** : Citoyen
* **Objectif** : Lire la ressource (contenu, vidéo, audio, exercices).
* **Scénario** :

  1. L’utilisateur ouvre une fiche ressource.
  2. Le système affiche : description, média, commentaires, auteurs.
* **Extension** :

  * Jouer un média (audio/vidéo accessible RGAA).

---

### UC4 — **Commenter une ressource**

* **Acteur** : Citoyen connecté
* **Objectif** : Partager son avis/expérience.
* **Scénario** :

  1. L’utilisateur rédige un commentaire.
  2. Le système vérifie la conformité (filtre anti-spam).
  3. Le commentaire passe en “En attente” ou “Publié automatiquement” selon règles.
* **Variation** :

  * Peut être soumis via modération automatisée.
* **Contraintes** :

  * Anonymisation possible (pseudo au lieu du nom réel).

---

### UC5 — **Signaler un contenu problématique**

* **Acteur** : Citoyen connecté
* **Objectif** : Assurer une communauté saine.
* **Scénario** :

  1. L’utilisateur clique “Signaler”.
  2. Choisit un motif (violence, discrimination, hors sujet…).
  3. Le système crée une entrée dans la file de modération.

---

### UC6 — **Ajouter aux favoris**

* **Acteur** : Citoyen connecté
* **Objectif** : Garder une liste personnelle de ressources utiles.
* **Scénario** :

  1. L’utilisateur appuie sur “Favori”.
  2. Le système enregistre en base et met à jour le tableau de bord utilisateur.

---

### UC7 — **Partage d’une ressource**

* **Acteur** : Citoyen connecté
* **Objectif** : Partager via email, réseaux sociaux, lien.
* **Scénario** :

  1. L’utilisateur clique “Partager”.
  2. Le système génère un lien ou déclenche une API de partage.
  3. Le partage est loggé dans la progression utilisateur (gamification).

---

### UC8 — **Suivre sa progression (Gamification)**

* **Acteur** : Citoyen connecté
* **Objectif** : Visualiser son engagement.
* **Scénario** :

  1. L’utilisateur accède à “Mon Espace”.
  2. Le système affiche badges, niveaux, statistiques.
* **Contraintes** :

  * Données synthétiques, jamais sensibles.

---

## 3. Cas d’usage — Modérateurs

### UC9 — **Consulter la liste des contenus signalés**

* **Acteur** : Modérateur
* **Objectif** : Traiter les signalements.
* **Scénario** :

  1. Le modérateur ouvre le tableau de modération.
  2. Les signalements sont listés par priorité.
  3. Il en choisit un à traiter.

---

### UC10 — **Valider / Refuser un commentaire**

* **Acteur** : Modérateur
* **Objectif** : Approuver ou retirer du contenu.
* **Scénario** :

  1. Le modérateur lit le commentaire signalé.
  2. Il clique “Valider” ou “Supprimer”.
  3. Le système met à jour l’état (publié / archivé).
  4. Notification possible à l'auteur.

---

### UC11 — **Bannir temporairement un utilisateur (si règles violées)**

* **Acteur** : Modérateur
* **Objectif** : Protéger la communauté.
* **Scénario** :

  1. Le modérateur ouvre le profil d’un utilisateur signalé.
  2. Il choisit “Suspendre X jours”.
  3. Le système enregistre une suspension limitée.

---

## 4. Cas d’usage — Administrateurs

### UC12 — **Créer / Modifier / Supprimer une ressource**

* **Acteur** : Administrateur
* **Objectif** : Gérer le catalogue.
* **Scénario** :

  1. Formulaire CRUD complet (titre, type, contenu, tags).
  2. Upload des médias (image, PDF, audio, vidéo).
  3. Sauvegarde versionnée.
* **Contraintes** :

  * Vérification RGAA (contrastes, descriptions d'images obligatoires).
  * Métadonnées obligatoires (type, thème, durée).

---

### UC13 — **Gérer les catégories / tags**

* **Acteur** : Administrateur
* **Objectif** : Structuration du catalogue.

---

### UC14 — **Gérer les utilisateurs**

* **Acteur** : Administrateur
* **Objectif** : Gestion attributs, rôles, activation/désactivation.

---

### UC15 — **Consulter les statistiques globales**

* **Acteur** : Administrateur
* **Objectif** : Analyse d’usage.
* **Données typiques** :

  * nombre de connexions,
  * ressources les plus consultées,
  * créations de comptes,
  * taux de participation.

---

## 5. Cas d’usage — Super-administrateur

### UC16 — **Gérer les rôles et permissions**

* **Objectif** : Définir granularité fine des accès.

---

### UC17 — **Configurer les paramètres du système**

* **Objectif** : Ajuster :

  * règles de modération,
  * politique de données (durée conservation),
  * activation/desactivation modules (gamification, recherche avancée).

---

### UC18 — **Audit & conformité RGPD**

* **Acteur** : Super-administrateur
* **Objectif** : Exports, suppression complète des données, consultation des logs.

---

## 6. Bonus — Cas d’usage transverses

### UC19 — **Backup & restauration**

* Automatisé ; déclenchable par super-admin.

### UC20 — **Tests d’accessibilité (RGAA)**

* Intégrés dans le pipeline CI/CD.

### UC21 — **Notifications (email / push)**

* Utilisateur reçoit notifications (nouveaux commentaires, réponses, badges).

---

# ✔️ Conclusion

Ces cas d’usage couvrent :

* la navigation citoyenne,
* les interactions sociales,
* la modération,
* l’administration du catalogue,
* la conformité et la gestion opérationnelle.

Si vous le souhaitez, je peux produire :
✅ un **diagramme UML "Use Case"** en Mermaid,
✅ des **User Stories** au format Agile,
✅ ou une **matrice Acteurs × Use Cases**.
