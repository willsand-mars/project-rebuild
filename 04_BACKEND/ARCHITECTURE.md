# Backend Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'architecture générale du Backend de Project Rebuild.

Son objectif est de garantir une organisation modulaire, maintenable et évolutive, indépendante des frameworks et des technologies d'implémentation.

---

# 2. Principes

L'architecture repose sur les principes suivants :

* Domain-Driven Design ;
* Clean Architecture ;
* SOLID ;
* CQRS ;
* Dependency Injection ;
* Event-Driven Architecture.

---

# 3. Couches

Le Backend est organisé en couches clairement séparées.

```text
Presentation
        │
        ▼
Application
        │
        ▼
Domain
        │
        ▼
Infrastructure
```

Chaque couche ne dépend que des couches situées en dessous selon les règles de la Clean Architecture.

---

# 4. Presentation Layer

Responsabilités :

* recevoir les requêtes externes ;
* valider leur format ;
* authentifier les utilisateurs ;
* transformer les réponses.

Cette couche ne contient aucune logique métier.

---

# 5. Application Layer

Responsabilités :

* exécuter les cas d'usage ;
* coordonner les Repositories ;
* invoquer les Business Engines ;
* gérer les transactions applicatives ;
* publier les événements.

Elle orchestre le Domaine sans modifier ses règles.

---

# 6. Domain Layer

Cette couche contient :

* Entités ;
* Value Objects ;
* Domain Services ;
* Domain Events ;
* Business Engines.

Elle constitue le cœur du logiciel.

---

# 7. Infrastructure Layer

Responsabilités :

* accès aux bases de données ;
* stockage de fichiers ;
* systèmes de messagerie ;
* cache ;
* services externes ;
* fournisseurs techniques.

L'infrastructure implémente des interfaces définies par les couches supérieures.

---

# 8. Dépendances

Les dépendances suivent toujours cette règle :

```text
Presentation
        ↓
Application
        ↓
Domain
        ↑
Infrastructure
```

Le Domaine ne dépend jamais de l'Infrastructure.

---

# 9. Cas d'usage

Chaque action utilisateur est implémentée sous la forme d'un cas d'usage unique.

Un cas d'usage :

* reçoit une commande ou une requête ;
* orchestre les composants nécessaires ;
* produit un résultat déterministe.

---

# 10. Événements

Les événements métier produits par le Domaine sont relayés par la couche Application.

Ils peuvent être consommés par :

* d'autres cas d'usage ;
* des traitements asynchrones ;
* les projections ;
* les notifications.

---

# 11. Testabilité

Chaque couche doit pouvoir être testée indépendamment.

Les dépendances sont injectées via des interfaces.

Les composants métiers restent isolés des technologies.

---

# 12. Invariants

L'architecture garantit toujours :

* aucune logique métier dans la couche Presentation ;
* aucune logique métier dans l'Infrastructure ;
* dépendances dirigées vers le Domaine ;
* composants remplaçables ;
* forte modularité ;
* haute testabilité.

---

# 13. Résumé

L'architecture Backend de Project Rebuild applique les principes de la Clean Architecture et du Domain-Driven Design afin d'assurer une séparation stricte des responsabilités, une évolutivité à long terme et une indépendance vis-à-vis des technologies d'implémentation.
