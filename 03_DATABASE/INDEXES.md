# Database Index Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie d'indexation de Project Rebuild.

Les index ont pour objectif d'optimiser les performances de lecture tout en préservant l'intégrité du domaine.

Ils ne modifient jamais les règles métier.

---

# 2. Principes

Chaque index doit :

* répondre à un besoin identifié ;
* améliorer les performances de lecture ;
* limiter le coût des écritures ;
* rester indépendant du moteur de base de données.

Les index ne sont jamais utilisés pour implémenter une logique métier.

---

# 3. Catégories d'index

## Primary Index

Chaque agrégat possède un identifiant unique.

Exemples :

* UserId
* MissionId
* HabitId
* BadgeId

---

## Foreign Reference Index

Optimise les recherches par relation.

Exemples :

* UserId
* MissionId
* HabitId

---

## Time Index

Optimise les recherches chronologiques.

Exemples :

* CreatedAt
* UpdatedAt
* CompletedAt
* EventDate

---

## Status Index

Optimise les recherches selon l'état métier.

Exemples :

* MissionStatus
* HabitStatus
* NotificationStatus

---

## Composite Index

Combine plusieurs critères fréquemment utilisés ensemble.

Exemples :

* UserId + CreatedAt
* UserId + Status
* UserId + EventDate

---

# 4. Domain Events

Les événements doivent être indexés notamment par :

* EventId
* AggregateId
* EventType
* OccurredAt

Cela garantit une reconstruction rapide des historiques.

---

# 5. Analytics

Les projections analytiques peuvent disposer d'index dédiés afin d'optimiser :

* tableaux de bord ;
* statistiques ;
* historiques.

Ces index ne doivent jamais influencer les données métier.

---

# 6. Recherche

Les recherches utilisateur doivent privilégier :

* identifiants ;
* états ;
* périodes ;
* catégories.

Les recherches textuelles restent indépendantes de cette spécification.

---

# 7. Évolution

Les index peuvent évoluer sans modifier :

* le domaine ;
* les Engines ;
* les contrats métier.

Ils constituent une optimisation d'infrastructure.

---

# 8. Contraintes

Un index ne doit jamais :

* imposer une règle métier ;
* modifier une donnée ;
* créer un effet de bord.

---

# 9. Invariants

Tous les index respectent les règles suivantes :

* indépendance technologique ;
* optimisation uniquement ;
* cohérence permanente ;
* absence de logique métier.

---

# 10. Résumé

La stratégie d'indexation de Project Rebuild garantit des performances élevées tout en conservant une séparation stricte entre les optimisations de stockage et les règles du domaine.
