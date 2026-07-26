# 02_ENGINES/STREAK_ENGINE.md

# Streak Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Streak Engine** est responsable de la gestion des séries (Streaks).

Une série représente une succession ininterrompue d'actions conformes aux règles métier.

Elle matérialise la continuité de l'effort, pilier fondamental de la philosophie de Project Rebuild.

---

# 2. Responsabilités

Le Streak Engine est responsable de :

* créer une série ;
* prolonger une série ;
* interrompre une série ;
* calculer sa durée ;
* publier les événements associés.

Il n'est jamais responsable de :

* valider une habitude ;
* attribuer de l'XP ;
* gérer les niveaux ;
* envoyer des notifications.

---

# 3. Principes métier

## La continuité avant l'intensité

Une longue série de petites actions possède davantage de valeur qu'un effort exceptionnel isolé.

---

## Neutralité

La rupture d'une série n'est jamais considérée comme un échec.

Elle constitue uniquement un fait métier.

---

## Résilience

Le moteur autorise toujours la création d'une nouvelle série.

Aucune rupture n'empêche une future progression.

---

# 4. Entrées

Le moteur consomme :

* HabitCompleted ;
* MissionCompleted ;
* tout autre événement explicitement autorisé par le domaine.

---

# 5. Cycle de vie

```text
Inactive
    ↓
Started
    ↓
Active
        │
        ├── Extended
        │
        └── Broken
```

Chaque transition est déterminée par les règles métier.

---

# 6. Calcul

Le moteur calcule notamment :

* longueur actuelle ;
* meilleure série ;
* date de début ;
* dernière validation ;
* durée totale.

Les règles de calcul restent indépendantes de toute technologie.

---

# 7. Sorties

Le moteur produit un **Streak Report** contenant :

* état ;
* longueur actuelle ;
* record personnel ;
* historique ;
* horodatage ;
* version des règles.

Le rapport est immuable.

---

# 8. Interactions

Le Streak Engine publie des événements consommés notamment par :

* XP Engine ;
* Badge Engine ;
* Achievement Engine ;
* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine.

---

# 9. Contraintes

Le moteur garantit :

* une seule série active par contexte métier ;
* calcul reproductible ;
* historique complet ;
* traitement idempotent.

---

# 10. Événements publiés

Le moteur peut publier :

* StreakStarted
* StreakExtended
* StreakBroken
* NewPersonalBestStreak

---

# 11. Invariants

* une série est calculée uniquement à partir de faits métier ;
* aucun calcul manuel ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à l'infrastructure ;
* toutes les transitions sont déterministes.

---

# 12. Dépendances

Le Streak Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

Il ne dépend d'aucun moteur de récompense.

---

# 13. Résumé

Le Streak Engine mesure la continuité des comportements de l'utilisateur. Il transforme les validations successives en indicateurs de discipline, publie les événements de progression associés et fournit une référence fiable aux moteurs de récompenses, d'analyse et au Rebuild Engine, tout en restant totalement indépendant de la couche technique.
