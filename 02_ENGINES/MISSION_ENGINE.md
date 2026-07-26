# Mission Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Mission Engine** est responsable de la gestion du cycle de vie des missions.

Une mission représente une action concrète permettant à l'utilisateur de progresser dans son parcours de reconstruction.

Le moteur décide de l'état des missions mais ne crée pas leur interface de présentation.

---

# 2. Responsabilités

Le Mission Engine est responsable de :

* valider les conditions d'une mission ;
* suivre son état ;
* détecter sa complétion ;
* gérer les échéances ;
* publier les événements associés.

Il n'est jamais responsable de :

* attribuer l'XP ;
* débloquer des badges ;
* envoyer des notifications ;
* calculer le RBI.

---

# 3. Cycle de vie

Une mission peut évoluer entre les états suivants :

```text
Created
    ↓
Available
    ↓
Active
    ↓
Completed
        │
        └── Failed (si les règles métier le permettent)
```

Les transitions sont exclusivement pilotées par les règles métier.

---

# 4. Entrées

Le moteur consomme :

* les Missions définies dans le domaine ;
* les actions validées de l'utilisateur ;
* les événements métier nécessaires à l'évaluation des conditions.

---

# 5. Validation

Pour chaque action reçue, le moteur vérifie :

* les prérequis ;
* les critères de réussite ;
* les éventuelles contraintes temporelles ;
* les dépendances métier.

Une mission n'est validée que si toutes les conditions sont satisfaites.

---

# 6. Sorties

Le moteur produit un **Mission Report** contenant notamment :

* identifiant de la mission ;
* état courant ;
* progression ;
* date de validation ;
* version des règles métier ;
* horodatage.

Le rapport est immuable.

---

# 7. Principes métier

## Une mission représente un engagement

Elle possède toujours un objectif clairement défini.

---

## Validation objective

Une mission est validée uniquement à partir de faits métier.

---

## Explicabilité

Le moteur doit pouvoir expliquer pourquoi une mission est :

* disponible ;
* active ;
* terminée ;
* non validée.

---

## Reproductibilité

Pour les mêmes données, le résultat est toujours identique.

---

# 8. Interactions

Le Mission Engine publie des événements consommés notamment par :

* XP Engine ;
* Habit Engine ;
* Streak Engine ;
* Badge Engine ;
* Achievement Engine ;
* Rebuild Engine ;
* Coach Engine.

Il ne connaît jamais ses consommateurs.

---

# 9. Contraintes

Le moteur garantit :

* aucune validation multiple ;
* transitions d'état cohérentes ;
* traitement idempotent ;
* historique complet.

---

# 10. Événements publiés

Le moteur peut publier :

* MissionCreated
* MissionAvailable
* MissionStarted
* MissionProgressUpdated
* MissionCompleted
* MissionFailed

Ces événements représentent uniquement des faits métier.

---

# 11. Invariants

* une mission possède un état unique ;
* une mission terminée ne peut être validée une seconde fois ;
* les transitions suivent le cycle de vie défini ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à la technologie utilisée.

---

# 12. Dépendances

Le Mission Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

Il ne dépend d'aucun moteur de récompense.

---

# 13. Résumé

Le Mission Engine pilote l'ensemble du cycle de vie des missions. Il applique les règles métier permettant de déterminer leur état, publie les événements associés et constitue la source de vérité concernant la progression opérationnelle de l'utilisateur, tout en restant indépendant des mécanismes de récompense et de présentation.
