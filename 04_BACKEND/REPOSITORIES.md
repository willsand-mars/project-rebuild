# Repositories

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Les **Repositories** assurent l'accès aux agrégats persistés du Domaine.

Ils encapsulent les mécanismes de stockage afin que le Domaine et les Application Services restent indépendants des technologies utilisées.

---

# 2. Responsabilités

Un Repository est responsable de :

* charger un agrégat ;
* persister un agrégat ;
* supprimer logiquement un agrégat lorsque les règles le permettent ;
* rechercher un agrégat selon des critères métier.

Il n'est jamais responsable de :

* appliquer une règle métier ;
* calculer un indicateur ;
* gérer une transaction ;
* effectuer une validation métier.

---

# 3. Principes

Chaque Repository respecte les principes suivants :

* une responsabilité métier ;
* une interface stable ;
* indépendance de la technologie ;
* forte testabilité.

---

# 4. Relation avec les agrégats

En règle générale :

* un Repository gère un Aggregate Root ;
* les objets internes de l'agrégat ne sont jamais manipulés indépendamment.

Cette règle garantit la cohérence du Domaine.

---

# 5. Interfaces

Les interfaces des Repositories sont définies dans le Domaine.

Leur implémentation appartient à la couche Infrastructure.

Cette inversion de dépendance garantit le découplage du système.

---

# 6. Chargement

Le Repository restitue un agrégat cohérent et valide.

Les détails liés au stockage (jointures, requêtes, documents, cache, etc.) restent masqués.

---

# 7. Persistance

La persistance intervient uniquement après la réussite complète du cas d'usage.

Elle est généralement coordonnée par le **Unit of Work**.

---

# 8. Testabilité

Les Repositories peuvent être remplacés par des implémentations de test sans modifier les Application Services ni le Domaine.

---

# 9. Invariants

Les Repositories respectent toujours les règles suivantes :

* aucune logique métier ;
* aucune dépendance au Frontend ;
* aucune dépendance aux API ;
* interfaces définies par le Domaine ;
* implémentations portées par l'Infrastructure.

---

# 10. Résumé

Les Repositories assurent la persistance des agrégats tout en protégeant le Domaine des détails techniques. Ils constituent un point de découplage essentiel entre la logique métier et l'infrastructure de stockage.
