# Business Engines

**Version :** 1.0
**Statut :** Validé

---

# Objectif

Les **Business Engines** constituent la couche décisionnelle de Project Rebuild.

Ils implémentent les règles métier qui transforment les données du domaine en décisions, indicateurs et événements exploitables par le reste du système.

Ils représentent le cœur fonctionnel de l'application.

Aucun Engine ne dépend de l'interface utilisateur, de la base de données, du framework ou de l'intelligence artificielle.

---

# Position dans l'architecture

```text
Vision
    ↓
Domain
    ↓
Business Engines
    ↓
Infrastructure
    ↓
Backend
    ↓
Frontend
    ↓
Coach IA
```

Les Engines s'appuient exclusivement sur les objets du domaine.

---

# Principes

Tous les Engines respectent les principes suivants :

* responsabilité unique ;
* déterminisme ;
* reproductibilité ;
* explicabilité ;
* testabilité ;
* découplage ;
* indépendance technologique ;
* publication de Domain Events.

Les Engines ne modifient jamais directement l'interface utilisateur.

Ils publient uniquement des faits métier.

---

# Catalogue des Engines

## Core

* Rebuild Engine
* XP Engine
* Level Engine

## Progression

* Mission Engine
* Habit Engine
* Streak Engine

## Récompenses

* Badge Engine
* Achievement Engine

## Santé

* Nutrition Engine
* Body Engine
* Health Engine

## Assistance

* Coach Engine
* Notification Engine

## Analyse

* Analytics Engine

---

# Communication

Les Engines communiquent uniquement au travers :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

Les dépendances directes entre Engines doivent rester minimales.

---

# Invariants

Tous les Engines doivent respecter les règles suivantes :

* aucune logique d'interface ;
* aucune dépendance à la base de données ;
* aucune dépendance au framework ;
* aucune logique spécifique à l'IA ;
* aucune décision non explicable ;
* aucun effet de bord caché.

---

# Philosophie

Chaque Engine répond à une seule question métier.

Exemples :

* Quel est le niveau de progression ?
* Combien d'XP doit être accordée ?
* Une mission est-elle terminée ?
* Une habitude est-elle validée ?
* Un badge doit-il être débloqué ?

Cette séparation garantit une architecture modulaire, maintenable et évolutive sur le long terme.
