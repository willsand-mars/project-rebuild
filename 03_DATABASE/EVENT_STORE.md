# Event Store

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

L'Event Store constitue le registre immuable des Domain Events produits par Project Rebuild.

Il permet de conserver l'historique complet des faits métier ayant conduit à l'état actuel du système.

Il ne remplace pas les agrégats persistés.

Il complète leur représentation.

---

# 2. Principes

L'Event Store poursuit plusieurs objectifs :

* historiser les événements métier ;
* reconstruire un état passé ;
* alimenter les projections ;
* garantir la traçabilité.

Chaque événement représente un fait métier définitivement validé.

---

# 3. Nature des événements

Les événements enregistrés décrivent exclusivement ce qui s'est produit.

Exemples :

* MissionCompleted
* HabitCompleted
* XPGained
* LevelReached
* BadgeUnlocked
* RebuildIndexCalculated

Ils ne décrivent jamais une intention.

---

# 4. Immutabilité

Une fois enregistré :

* un événement ne peut pas être modifié ;
* un événement ne peut pas être remplacé ;
* un événement ne peut pas être supprimé (hors politique exceptionnelle documentée).

Toute correction produit un nouvel événement.

---

# 5. Structure minimale

Chaque événement possède notamment :

* EventId ;
* AggregateId ;
* AggregateType ;
* EventType ;
* OccurredAt ;
* Version ;
* Payload.

La structure détaillée dépendra de l'implémentation.

---

# 6. Reconstruction

L'Event Store permet de :

* reconstruire un agrégat ;
* reconstruire un historique ;
* régénérer des projections ;
* rejouer des traitements si nécessaire.

---

# 7. Consommation

Les consommateurs possibles sont notamment :

* Analytics Engine ;
* Coach Engine ;
* projections de lecture ;
* outils d'audit.

Les Business Engines publient les événements mais ne lisent pas directement l'Event Store pour leurs décisions métier.

---

# 8. Contraintes

Le système garantit :

* ordre chronologique ;
* identifiant unique ;
* intégrité des événements ;
* conservation des versions.

---

# 9. Invariants

L'Event Store respecte toujours les règles suivantes :

* uniquement des Domain Events ;
* aucune logique métier ;
* aucune modification rétroactive ;
* stockage immuable ;
* indépendance de la technologie utilisée.

---

# 10. Résumé

L'Event Store constitue la mémoire historique de Project Rebuild. Il conserve l'ensemble des faits métier validés afin de garantir la traçabilité, la reconstruction du système et l'alimentation des projections analytiques, tout en restant indépendant des choix d'implémentation.
