# Frontend Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'architecture générale du Frontend de Project Rebuild.

L'objectif est de créer une interface durable, évolutive et maintenable capable de supporter l'évolution du produit pendant plusieurs années.

---

# 2. Principes

L'architecture Frontend respecte :

* séparation des responsabilités ;
* composants réutilisables ;
* logique métier externalisée ;
* forte testabilité ;
* faible couplage ;
* évolutivité.

---

# 3. Architecture générale

```text
UI Layer
    ↓
Presentation Logic
    ↓
Application Client Layer
    ↓
Backend API
```

---

# 4. UI Layer

Responsabilités :

* affichage ;
* interaction utilisateur ;
* animations ;
* composants visuels.

Cette couche ne contient aucune décision métier.

---

# 5. Presentation Logic

Responsabilités :

* préparation des données pour l'affichage ;
* gestion des états d'écran ;
* orchestration des interactions locales.

Elle adapte les données reçues sans les interpréter comme règles métier.

---

# 6. Application Client Layer

Responsabilités :

* communication API ;
* gestion des requêtes ;
* transformation des réponses ;
* gestion des erreurs côté client.

---

# 7. Composants

Les composants doivent être :

* indépendants ;
* réutilisables ;
* testables ;
* spécialisés.

Exemples conceptuels :

* Mission Card ;
* XP Display ;
* Level Indicator ;
* Avatar View ;
* Coach Panel.

---

# 8. Gestion d'état

L'état Frontend doit distinguer :

## État serveur

Données provenant du Backend :

* profil ;
* missions ;
* progression ;
* statistiques.

## État local

Données liées à l'interface :

* navigation ;
* animations ;
* préférences visuelles temporaires.

---

# 9. Communication Backend

Le Frontend communique uniquement via les contrats API définis par le Backend.

Il ne connaît pas :

* la base de données ;
* les Repositories ;
* les Engines internes.

---

# 10. Performance

L'architecture doit permettre :

* chargement rapide ;
* optimisation du rendu ;
* gestion efficace des ressources ;
* expérience fluide.

---

# 11. Invariants

Le Frontend respecte toujours :

* aucune logique métier ;
* aucune dépendance directe au Domaine ;
* aucune dépendance directe à la base de données ;
* séparation UI / logique applicative ;
* composants évolutifs.

---

# 12. Résumé

L'architecture Frontend de Project Rebuild garantit une interface moderne, immersive et durable. Elle transforme les capacités du système en expérience utilisateur tout en conservant une séparation stricte avec la logique métier.
