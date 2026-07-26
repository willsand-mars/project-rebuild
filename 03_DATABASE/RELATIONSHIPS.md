# Relationships

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les relations conceptuelles entre les agrégats persistés.

Il décrit les dépendances de données sans imposer un modèle relationnel ou documentaire.

---

# 2. Principes

Les relations doivent respecter les règles suivantes :

* faible couplage ;
* forte cohérence métier ;
* dépendances explicites ;
* absence de cycles inutiles.

---

# 3. Racine principale

Le principal point d'ancrage est :

```text
User
```

Toutes les données utilisateur sont rattachées à cette identité.

---

# 4. Relations de progression

```text
User
│
├── XP
├── Levels
└── RebuildIndexes
```

Chaque utilisateur possède son propre historique de progression.

---

# 5. Relations des missions

```text
User
│
├── Missions
└── MissionHistory
```

Une mission appartient toujours à un utilisateur.

---

# 6. Relations des habitudes

```text
User
│
├── Habits
├── HabitExecutions
└── HabitHistory
```

---

# 7. Relations des récompenses

```text
User
│
├── UserBadges
└── UserAchievements
```

Les définitions de Badges et Achievements restent indépendantes des utilisateurs.

---

# 8. Relations santé

```text
User
│
├── NutritionLogs
├── BodyMeasurements
├── SleepLogs
└── RecoveryLogs
```

---

# 9. Relations analytiques

Les projections analytiques dépendent des événements métier.

Elles ne constituent jamais la source de vérité.

```text
Domain Events
        │
        ▼
Analytics Projections
```

---

# 10. Relations des événements

Tous les événements du domaine référencent :

* un agrégat ;
* un identifiant métier ;
* une date ;
* une version.

Ils restent immuables.

---

# 11. Intégrité référentielle

Toute référence persistée doit :

* pointer vers un agrégat existant ;
* respecter les contraintes métier ;
* rester cohérente dans le temps.

Les références orphelines sont interdites.

---

# 12. Couplage

Les relations doivent rester minimales.

Chaque agrégat doit pouvoir évoluer indépendamment tant que son contrat métier est respecté.

---

# 13. Invariants

Les relations respectent toujours les règles suivantes :

* aucun cycle métier ;
* aucune dépendance cachée ;
* aucune duplication inutile ;
* cohérence référentielle permanente ;
* indépendance de la technologie de stockage.

---

# 14. Résumé

Le modèle relationnel de Project Rebuild privilégie des agrégats faiblement couplés et fortement cohérents. Les relations sont guidées par le Domaine et non par les contraintes d'un SGBD, garantissant une architecture pérenne et évolutive.
