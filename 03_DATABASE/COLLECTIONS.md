# Persistent Collections

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les collections (ou tables selon la technologie utilisée) qui constituent le modèle de persistance de Project Rebuild.

Chaque collection représente un agrégat ou un ensemble de données cohérent issu du Domaine.

Les noms décrits ici sont indépendants du moteur de base de données.

---

# 2. Principes

Chaque collection doit :

* représenter une seule responsabilité métier ;
* posséder une clé primaire immuable ;
* être versionnable ;
* être historisable lorsque nécessaire ;
* rester indépendante de la couche applicative.

---

# 3. Collections métier

## Identity

Stocke les informations d'identité de l'utilisateur.

Exemples :

* User
* Profile
* Preferences

---

## Progression

Stocke la progression globale.

Collections :

* XP
* Levels
* RebuildIndexes

---

## Missions

Stocke :

* Missions
* MissionProgress
* MissionHistory

---

## Habits

Stocke :

* Habits
* HabitExecutions
* HabitHistory

---

## Streaks

Stocke :

* Streaks
* StreakHistory

---

## Rewards

Stocke :

* Badges
* UserBadges
* Achievements
* UserAchievements

---

## Nutrition

Stocke :

* Meals
* NutritionLogs
* NutritionGoals

---

## Body

Stocke :

* BodyMeasurements
* WeightHistory
* ProgressPhotos

---

## Health

Stocke :

* HealthIndicators
* SleepLogs
* RecoveryLogs

---

## Analytics

Stocke :

* AnalyticsSnapshots
* DashboardProjections

---

## Notifications

Stocke :

* NotificationQueue
* NotificationHistory

---

## Audit

Stocke :

* AuditLogs
* DomainEvents
* EngineReports

---

# 4. Responsabilités

Chaque collection appartient à un seul contexte métier.

Les données ne doivent jamais être dupliquées entre collections sans justification architecturale.

---

# 5. Lecture et écriture

Les collections d'écriture constituent la source de vérité.

Les collections de lecture peuvent être reconstruites à partir des données métier.

---

# 6. Invariants

Toutes les collections respectent les règles suivantes :

* identifiant immuable ;
* horodatage UTC ;
* version métier ;
* intégrité référentielle ;
* aucune logique métier.

---

# 7. Résumé

Les collections de Project Rebuild reflètent directement les agrégats du Domaine. Elles sont organisées par responsabilité métier afin de garantir une architecture de persistance claire, modulaire et évolutive.
