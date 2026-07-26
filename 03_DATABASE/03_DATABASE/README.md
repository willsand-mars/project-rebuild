# Database Architecture

**Version :** 1.0
**Statut :** Validé

---

# Objectif

Le dossier **03_DATABASE** définit l'architecture de persistance de Project Rebuild.

Cette couche décrit **comment le domaine est stocké**, sans dépendre d'une technologie particulière.

Elle ne décrit ni PostgreSQL, ni MongoDB, ni Supabase.

Elle décrit le modèle de persistance métier.

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
Frontend
```

La base de données est une conséquence du domaine.

Elle n'influence jamais les règles métier.

---

# Principes

La persistance respecte les principes suivants :

* séparation du domaine et du stockage ;
* indépendance technologique ;
* traçabilité complète ;
* historisation des événements ;
* cohérence des données ;
* évolutivité ;
* performances de lecture ;
* sécurité des données.

---

# Philosophie

La base de données est considérée comme une infrastructure.

Elle ne contient aucune logique métier.

Les règles métier appartiennent exclusivement :

* au Domain ;
* aux Business Engines.

---

# Contenu du dossier

Ce dossier documente :

* l'organisation des données ;
* les collections ou tables ;
* les relations ;
* les contraintes d'intégrité ;
* les index ;
* les politiques de suppression ;
* le versionnement ;
* l'audit ;
* les migrations ;
* les conventions de nommage.

---

# Objectifs

Cette documentation permet de garantir :

* une base cohérente ;
* une évolution maîtrisée ;
* des migrations sûres ;
* une maintenance simplifiée ;
* une indépendance vis-à-vis des technologies de stockage.

---

# Règles fondamentales

La persistance ne doit jamais :

* contenir de logique métier ;
* modifier les décisions des Engines ;
* dépendre de l'interface utilisateur ;
* dépendre de l'intelligence artificielle.

Elle constitue uniquement la représentation persistante du domaine.
