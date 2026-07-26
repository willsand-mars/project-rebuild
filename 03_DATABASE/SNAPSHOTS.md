# Snapshot Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de gestion des **Snapshots** de Project Rebuild.

Un Snapshot représente une photographie cohérente de l'état d'un agrégat ou d'un ensemble de données à un instant donné.

Les Snapshots sont utilisés comme mécanisme d'optimisation.

Ils ne remplacent jamais les Domain Events.

---

# 2. Principes

Les Snapshots permettent de :

* accélérer la reconstruction des agrégats ;
* réduire le temps de relecture des événements ;
* améliorer les performances ;
* conserver un état cohérent.

Ils ne constituent jamais la source de vérité.

---

# 3. Création

Un Snapshot peut être créé notamment :

* après un nombre défini d'événements ;
* après une étape importante ;
* à intervalles réguliers ;
* lors d'opérations de maintenance.

La politique exacte dépend de l'implémentation.

---

# 4. Contenu

Un Snapshot contient notamment :

* AggregateId ;
* AggregateType ;
* Version ;
* CreatedAt ;
* State.

Le contenu exact dépend de l'agrégat concerné.

---

# 5. Reconstruction

Pour reconstruire un agrégat :

1. chargement du Snapshot le plus récent ;
2. relecture des événements postérieurs ;
3. reconstruction de l'état courant.

Cette approche optimise les performances tout en garantissant la cohérence métier.

---

# 6. Historique

Les Snapshots peuvent être conservés afin de :

* faciliter les audits ;
* comparer des états ;
* accélérer des restaurations.

Leur politique de rétention est définie par l'infrastructure.

---

# 7. Contraintes

Les Snapshots garantissent :

* cohérence ;
* reproductibilité ;
* indépendance des Engines ;
* compatibilité avec l'Event Store.

---

# 8. Invariants

Les règles suivantes sont toujours respectées :

* un Snapshot est immuable après création ;
* un Snapshot ne modifie jamais le domaine ;
* un Snapshot ne remplace jamais les événements ;
* un Snapshot reste une optimisation de persistance.

---

# 9. Résumé

Les Snapshots améliorent les performances de reconstruction des agrégats sans remettre en cause l'architecture événementielle de Project Rebuild. Ils constituent une optimisation facultative, indépendante de la logique métier.
