# Backend Architecture

**Version :** 1.0
**Statut :** Validé

---

# Objectif

Le dossier **04_BACKEND** définit l'architecture applicative de Project Rebuild.

Cette couche fait le lien entre le Domaine, les Business Engines et les interfaces externes (Frontend, IA, API).

Le Backend exécute les cas d'usage.

Il n'implémente jamais les règles métier.

---

# Position dans l'architecture

```text
Vision
    ↓
Domain
    ↓
Business Engines
    ↓
Database
    ↓
Backend
    ↓
Frontend / IA / API
```

Le Backend orchestre les traitements.

Le Domaine prend les décisions.

---

# Responsabilités

Le Backend est responsable de :

* exposer les cas d'usage ;
* orchestrer les transactions ;
* appliquer les règles de sécurité ;
* gérer les accès aux données ;
* coordonner les Business Engines ;
* publier les événements applicatifs.

Le Backend n'est jamais responsable de :

* prendre une décision métier ;
* effectuer des calculs métier ;
* stocker une logique d'interface.

---

# Principes

Le Backend respecte les principes suivants :

* Clean Architecture ;
* Domain-Driven Design ;
* CQRS ;
* séparation des responsabilités ;
* forte testabilité ;
* faible couplage ;
* injection de dépendances ;
* observabilité.

---

# Contenu du dossier

Ce dossier documente notamment :

* l'architecture applicative ;
* les API ;
* les services applicatifs ;
* les commandes ;
* les requêtes ;
* la sécurité ;
* les traitements asynchrones ;
* la configuration ;
* la gestion des erreurs.

---

# Résumé

Le Backend constitue la couche d'orchestration de Project Rebuild. Il relie les interfaces au Domaine tout en garantissant une séparation stricte entre logique applicative, logique métier et infrastructure.
