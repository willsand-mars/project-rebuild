# Habit Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Habit Engine** est responsable de l'évaluation, du suivi et de la validation des habitudes (Habits).

Une habitude représente un comportement répété qui contribue à la reconstruction physique et mentale de l'utilisateur.

L'objectif du moteur est de mesurer la constance, jamais la perfection.

---

# 2. Responsabilités

Le Habit Engine est responsable de :

* suivre l'exécution des habitudes ;
* déterminer leur état ;
* mesurer leur régularité ;
* détecter leur validation ;
* publier les événements associés.

Il n'est jamais responsable de :

* créer des habitudes ;
* attribuer de l'XP ;
* gérer les séries (Streaks) ;
* calculer le RBI ;
* envoyer des notifications.

---

# 3. Cycle de vie

Une habitude évolue selon les états suivants :

```text
Created
    ↓
Scheduled
    ↓
Pending
    ↓
Completed
        │
        └── Missed
```

Les transitions sont exclusivement pilotées par les règles métier.

---

# 4. Entrées

Le moteur consomme :

* les définitions d'habitudes ;
* les actions validées de l'utilisateur ;
* les contraintes calendaires ;
* les événements du domaine.

---

# 5. Validation

Une habitude est considérée comme réalisée uniquement lorsque toutes les conditions métier sont satisfaites.

Le moteur ne réalise aucune estimation.

---

# 6. Régularité

Le moteur calcule des indicateurs de régularité tels que :

* fréquence de réalisation ;
* taux de réussite ;
* stabilité dans le temps ;
* historique d'exécution.

Ces indicateurs servent aux autres Engines mais ne constituent pas des récompenses.

---

# 7. Sorties

Le moteur produit un **Habit Report** contenant notamment :

* état courant ;
* progression ;
* taux de réussite ;
* indicateurs de régularité ;
* horodatage ;
* version des règles.

Le rapport est immuable.

---

# 8. Interactions

Le Habit Engine publie des événements pouvant être consommés par :

* XP Engine ;
* Streak Engine ;
* Badge Engine ;
* Achievement Engine ;
* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine.

---

# 9. Contraintes

Le moteur garantit :

* validation unique ;
* historique complet ;
* calcul déterministe ;
* indépendance technologique.

---

# 10. Événements publiés

Le moteur peut publier :

* HabitScheduled
* HabitStarted
* HabitCompleted
* HabitMissed
* HabitConsistencyUpdated

---

# 11. Invariants

* une habitude possède un état unique ;
* aucune validation multiple ;
* tous les calculs sont reproductibles ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à la base de données.

---

# 12. Dépendances

Le Habit Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 13. Résumé

Le Habit Engine constitue la référence métier concernant les habitudes. Il mesure la discipline quotidienne, garantit un suivi fiable de leur exécution et fournit les informations nécessaires aux autres Engines sans jamais gérer les récompenses ni la présentation.
