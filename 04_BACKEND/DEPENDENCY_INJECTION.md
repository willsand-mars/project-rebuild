# Dependency Injection

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

L'injection de dépendances permet de découpler les composants de Project Rebuild en remplaçant les dépendances directes par des abstractions.

Elle facilite les tests, la maintenance et l'évolution de l'application.

---

# 2. Principes

Le système respecte les principes suivants :

* inversion des dépendances ;
* faible couplage ;
* forte cohésion ;
* testabilité ;
* modularité.

---

# 3. Règle fondamentale

Les composants demandent leurs dépendances.

Ils ne les créent jamais eux-mêmes.

Cette règle garantit une architecture découplée.

---

# 4. Dépendances injectées

Peuvent être injectés notamment :

* Repositories ;
* Business Engines ;
* Application Services ;
* Services d'infrastructure ;
* Journalisation ;
* Cache ;
* Configuration.

---

# 5. Cycle de vie

Chaque dépendance possède un cycle de vie défini selon son rôle.

Exemples conceptuels :

* unique pour l'application ;
* partagé durant une requête ;
* créé à chaque utilisation.

Le choix exact dépend de l'implémentation.

---

# 6. Interfaces

Les composants dépendent d'interfaces et non d'implémentations concrètes.

Les implémentations sont fournies par la couche Infrastructure.

---

# 7. Testabilité

Grâce à l'injection de dépendances :

* les composants peuvent être testés isolément ;
* les dépendances peuvent être simulées ;
* les comportements peuvent être reproduits de manière déterministe.

---

# 8. Contraintes

L'injection de dépendances ne doit jamais :

* masquer les responsabilités ;
* créer des dépendances circulaires ;
* contourner les règles de la Clean Architecture.

---

# 9. Invariants

Le système respecte toujours les règles suivantes :

* dépendance vers des abstractions ;
* aucune instanciation directe dans le Domaine ;
* composants remplaçables ;
* architecture modulaire.

---

# 10. Résumé

L'injection de dépendances constitue un mécanisme essentiel de Project Rebuild. Elle garantit un faible couplage entre les composants, favorise la testabilité et permet à l'application d'évoluer sans remettre en cause son architecture fondamentale.
