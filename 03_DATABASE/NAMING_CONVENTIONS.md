# Database Naming Conventions

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les conventions de nommage utilisées dans la couche de persistance de Project Rebuild.

L'objectif est de garantir une base de données cohérente, lisible et maintenable pendant toute la durée de vie du produit.

Les conventions décrites ici sont indépendantes du moteur de base de données.

---

# 2. Principes

Toutes les conventions de nommage doivent respecter les critères suivants :

* cohérence ;
* lisibilité ;
* stabilité ;
* prévisibilité ;
* indépendance technologique.

Les noms ne doivent jamais dépendre d'un framework ou d'un langage.

---

# 3. Langue

L'ensemble des identifiants techniques est rédigé en anglais.

Les documents métier peuvent être rédigés dans une autre langue.

Les données utilisateur restent indépendantes de cette règle.

---

# 4. Collections

Les collections utilisent :

* PascalCase ;
* des noms explicites ;
* des noms métier.

Exemples :

```text
User
Mission
Habit
Achievement
NotificationHistory
DomainEvent
```

---

# 5. Champs

Les champs utilisent :

* camelCase ;
* noms complets ;
* vocabulaire métier.

Exemples :

```text
userId
createdAt
updatedAt
missionStatus
rebuildIndex
```

---

# 6. Identifiants

Toutes les clés primaires utilisent le suffixe :

```text
Id
```

Exemples :

```text
userId
habitId
missionId
badgeId
```

---

# 7. Dates

Les dates utilisent systématiquement le suffixe :

```text
At
```

Exemples :

```text
createdAt
updatedAt
completedAt
occurredAt
deletedAt
```

---

# 8. Booléens

Les booléens commencent par un préfixe explicite.

Exemples :

```text
isCompleted
isArchived
isDeleted
isActive
```

---

# 9. Énumérations

Les valeurs d'énumération utilisent :

* PascalCase ;
* noms métier.

Exemples :

```text
Completed
Pending
Cancelled
Active
```

---

# 10. Domain Events

Les événements sont nommés au passé.

Ils décrivent uniquement un fait métier.

Exemples :

```text
MissionCompleted
HabitCompleted
BadgeUnlocked
LevelReached
```

---

# 11. Rapports

Les rapports produits par les Engines utilisent le suffixe :

```text
Report
```

Exemples :

```text
XPReport
BodyReport
CoachContextReport
```

---

# 12. Projections

Les projections de lecture utilisent le suffixe :

```text
Projection
```

Exemples :

```text
DashboardProjection
AnalyticsProjection
```

---

# 13. Invariants

Toutes les conventions respectent les règles suivantes :

* aucun nom ambigu ;
* aucune abréviation non documentée ;
* aucune dépendance technologique ;
* vocabulaire conforme à l'Ubiquitous Language.

---

# 14. Résumé

Les conventions de nommage de Project Rebuild garantissent une architecture uniforme, lisible et durable. Elles facilitent la collaboration, limitent les ambiguïtés et assurent une cohérence entre le Domaine, les Engines et la couche de persistance.
