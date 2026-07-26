# Badge Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Badge Engine** est responsable de l'attribution des badges.

Un badge représente une reconnaissance permanente d'un accomplissement ou d'un comportement remarquable dans le parcours de reconstruction.

Contrairement aux succès (Achievements), un badge met en valeur une identité de progression plus qu'un événement ponctuel.

---

# 2. Responsabilités

Le Badge Engine est responsable de :

* évaluer les critères d'obtention ;
* attribuer les badges ;
* garantir l'unicité des récompenses ;
* conserver l'historique des badges obtenus ;
* publier les événements associés.

Il n'est jamais responsable de :

* calculer l'XP ;
* déterminer les niveaux ;
* créer des missions ;
* envoyer des notifications ;
* calculer le RBI.

---

# 3. Entrées

Le moteur consomme les faits métier publiés par les autres Engines, notamment :

* LevelReached
* HabitCompleted
* StreakExtended
* MissionCompleted
* RebuildIndexImproved

Le moteur ne déclenche jamais lui-même ces événements.

---

# 4. Critères d'attribution

Chaque badge est défini par :

* un identifiant unique ;
* un nom ;
* une description ;
* des critères métier ;
* des règles de visibilité ;
* une rareté éventuelle.

Les critères sont exclusivement définis par le domaine.

---

# 5. Attribution

Lorsqu'un événement est reçu :

1. les critères sont évalués ;
2. l'unicité est vérifiée ;
3. le badge est attribué si toutes les conditions sont satisfaites ;
4. l'historique est mis à jour ;
5. les événements métier sont publiés.

---

# 6. Sorties

Le moteur produit un **Badge Report** contenant :

* badge obtenu ;
* date d'attribution ;
* événement déclencheur ;
* version des règles métier ;
* horodatage.

Le rapport est immuable.

---

# 7. Principes métier

## Unicité

Un badge ne peut être obtenu qu'une seule fois.

---

## Explicabilité

Chaque badge doit être justifiable par des faits métier.

---

## Déterminisme

Les mêmes données produisent toujours le même résultat.

---

## Traçabilité

Chaque attribution est historisée.

---

# 8. Interactions

Le Badge Engine publie des événements consommés notamment par :

* Coach Engine ;
* Notification Engine ;
* Analytics Engine ;
* Rebuild Engine.

---

# 9. Contraintes

Le moteur garantit :

* aucune double attribution ;
* traitement idempotent ;
* historique complet ;
* indépendance technologique.

---

# 10. Événements publiés

Le moteur peut publier :

* BadgeUnlocked
* BadgeGranted
* BadgeCollectionUpdated

---

# 11. Invariants

* un badge est permanent ;
* une attribution est irréversible (hors administration) ;
* aucun badge sans critères métier ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à l'infrastructure.

---

# 12. Dépendances

Le Badge Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 13. Résumé

Le Badge Engine reconnaît les accomplissements durables de l'utilisateur. Il attribue des badges de manière déterministe, traçable et explicable, garantissant une collection cohérente qui reflète le parcours de progression sans dépendre de la couche technique.
