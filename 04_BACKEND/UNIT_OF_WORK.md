# Unit of Work

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Le **Unit of Work** coordonne l'ensemble des opérations de persistance réalisées durant un cas d'usage.

Son objectif est de garantir qu'une série de modifications est appliquée comme une seule unité de travail cohérente.

Le Unit of Work ne contient aucune logique métier.

---

# 2. Responsabilités

Le Unit of Work est responsable de :

* ouvrir un contexte transactionnel ;
* suivre les modifications des agrégats ;
* coordonner les Repositories ;
* valider les écritures ;
* annuler les modifications en cas d'échec.

Il n'est jamais responsable de :

* prendre une décision métier ;
* effectuer un calcul métier ;
* communiquer avec les interfaces utilisateur.

---

# 3. Principes

Le Unit of Work respecte les principes suivants :

* atomicité ;
* cohérence ;
* isolation ;
* durabilité ;
* indépendance technologique.

---

# 4. Cycle de vie

Le cycle d'un Unit of Work est le suivant :

```text
Début
   ↓
Chargement des agrégats
   ↓
Exécution du cas d'usage
   ↓
Suivi des modifications
   ↓
Validation
   ↓
Commit
   ↓
Publication des événements
```

En cas d'échec :

```text
Erreur
   ↓
Rollback
   ↓
Fin
```

---

# 5. Transactions

Chaque Unit of Work correspond à une transaction applicative.

Les transactions doivent être :

* courtes ;
* cohérentes ;
* entièrement reproductibles.

---

# 6. Repositories

Tous les Repositories participant à un même cas d'usage utilisent le même Unit of Work.

Cela garantit la cohérence des écritures.

---

# 7. Domain Events

Les Domain Events sont publiés uniquement après la validation réussie de la transaction.

Aucun événement ne doit être publié si la transaction échoue.

---

# 8. Gestion des erreurs

En cas d'échec :

* aucune modification partielle n'est conservée ;
* toutes les opérations sont annulées ;
* une erreur standardisée est propagée.

---

# 9. Invariants

Le Unit of Work respecte toujours les règles suivantes :

* une transaction par cas d'usage ;
* aucune logique métier ;
* commit unique ;
* rollback complet en cas d'erreur ;
* publication des événements uniquement après validation.

---

# 10. Résumé

Le Unit of Work garantit la cohérence transactionnelle de Project Rebuild en regroupant les opérations de persistance d'un cas d'usage dans une unité atomique, indépendante des technologies de stockage.
