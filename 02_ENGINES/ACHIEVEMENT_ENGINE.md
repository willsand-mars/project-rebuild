# Achievement Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Achievement Engine** est responsable de la gestion des succès (Achievements).

Un Achievement représente l'accomplissement d'un objectif métier clairement défini.

Il récompense une réalisation spécifique, contrairement au Badge qui valorise davantage un parcours ou un comportement.

---

# 2. Responsabilités

Le moteur est responsable de :

* suivre la progression des succès ;
* évaluer leurs conditions ;
* valider leur obtention ;
* historiser les récompenses ;
* publier les événements associés.

Il n'est jamais responsable de :

* attribuer de l'XP ;
* calculer les niveaux ;
* gérer les badges ;
* créer des missions ;
* envoyer des notifications.

---

# 3. Entrées

Le moteur consomme les événements du domaine tels que :

* MissionCompleted
* LevelReached
* HabitCompleted
* StreakExtended
* GoalReached
* XPGained

---

# 4. Définition d'un Achievement

Chaque Achievement possède :

* un identifiant unique ;
* un nom ;
* une description ;
* des critères d'obtention ;
* un état de progression ;
* une éventuelle catégorie.

---

# 5. Cycle de vie

```text
Locked
    ↓
In Progress
    ↓
Unlocked
```

Une fois débloqué, un Achievement reste définitivement acquis.

---

# 6. Évaluation

À chaque événement reçu :

1. le moteur identifie les Achievements concernés ;
2. met à jour leur progression ;
3. vérifie les critères ;
4. valide les succès terminés ;
5. publie les événements métier.

---

# 7. Sorties

Le moteur produit un **Achievement Report** contenant :

* Achievement concerné ;
* état ;
* progression ;
* date de validation ;
* version des règles ;
* horodatage.

Le rapport est immuable.

---

# 8. Principes métier

## Progression visible

Un Achievement peut évoluer progressivement avant d'être débloqué.

---

## Déterminisme

Les règles produisent toujours le même résultat.

---

## Traçabilité

Chaque étape importante est historisée.

---

## Explicabilité

Chaque succès obtenu doit pouvoir être expliqué.

---

# 9. Interactions

Le moteur publie des événements consommés notamment par :

* XP Engine ;
* Badge Engine ;
* Coach Engine ;
* Notification Engine ;
* Analytics Engine ;
* Rebuild Engine.

---

# 10. Contraintes

Le moteur garantit :

* aucun déblocage multiple ;
* progression cohérente ;
* historique complet ;
* calcul reproductible.

---

# 11. Événements publiés

Le moteur peut publier :

* AchievementProgressUpdated
* AchievementUnlocked
* AchievementCompleted

---

# 12. Invariants

* un Achievement possède un état unique ;
* un Achievement débloqué reste acquis ;
* les critères sont exclusivement métier ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à la base de données.

---

# 13. Dépendances

Le moteur dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 14. Résumé

Le Achievement Engine pilote l'ensemble du cycle de vie des succès de Project Rebuild. Il mesure leur progression, valide leur obtention et publie les événements associés de manière déterministe, traçable et indépendante de toute technologie.
