# Command Query Responsibility Segregation (CQRS)

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Project Rebuild adopte le principe **CQRS (Command Query Responsibility Segregation)** afin de séparer clairement les opérations d'écriture des opérations de lecture.

Cette séparation améliore la maintenabilité, les performances et l'évolutivité de l'application.

---

# 2. Principes

Le modèle repose sur deux responsabilités distinctes :

## Modèle d'écriture

Responsable de :

* modifier le Domaine ;
* exécuter les cas d'usage ;
* publier les Domain Events.

---

## Modèle de lecture

Responsable de :

* consulter les données ;
* construire les projections ;
* répondre aux besoins des interfaces.

---

# 3. Flux d'écriture

```text id="p1k8gq"
Client
    ↓
API
    ↓
Command
    ↓
Command Handler
    ↓
Application Service
    ↓
Domain
    ↓
Repositories
    ↓
Domain Events
```

---

# 4. Flux de lecture

```text id="e4r6nd"
Client
    ↓
API
    ↓
Query
    ↓
Query Handler
    ↓
Read Model
    ↓
Réponse
```

---

# 5. Avantages

Le découplage permet :

* d'optimiser indépendamment lecture et écriture ;
* d'améliorer les performances ;
* de simplifier les tests ;
* de faire évoluer chaque modèle indépendamment.

---

# 6. Projections

Les modèles de lecture peuvent être reconstruits à partir :

* des données persistées ;
* des Domain Events ;
* des Snapshots.

Ils ne constituent jamais la source de vérité.

---

# 7. Transactions

Les transactions concernent uniquement le modèle d'écriture.

Les lectures restent indépendantes des traitements transactionnels.

---

# 8. Cohérence

Le système accepte une cohérence éventuelle entre les modèles de lecture et d'écriture lorsque cela améliore les performances, sans remettre en cause la cohérence du Domaine.

---

# 9. Invariants

Le modèle CQRS garantit :

* séparation lecture/écriture ;
* absence de logique métier dans les Queries ;
* absence de lecture métier dans les Commands ;
* indépendance des projections.

---

# 10. Résumé

CQRS constitue un pilier de l'architecture de Project Rebuild. Il sépare les responsabilités de lecture et d'écriture afin de favoriser la performance, la modularité et l'évolutivité du système.
