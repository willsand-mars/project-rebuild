# Application Services

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Les **Application Services** orchestrent les cas d'usage de Project Rebuild.

Ils constituent la frontière entre les interfaces externes (API, Frontend, IA) et le Domaine.

Ils coordonnent les composants nécessaires sans contenir de logique métier.

---

# 2. Responsabilités

Les Application Services sont responsables de :

* recevoir les commandes et requêtes ;
* coordonner les Repositories ;
* invoquer les Business Engines ;
* gérer les transactions applicatives ;
* publier les événements applicatifs ;
* retourner les résultats attendus.

Ils ne sont jamais responsables de :

* prendre une décision métier ;
* effectuer des calculs métier ;
* accéder directement aux technologies d'infrastructure.

---

# 3. Principes

Chaque Application Service respecte les principes suivants :

* une responsabilité unique ;
* un cas d'usage unique ;
* orchestration uniquement ;
* absence de logique métier ;
* forte testabilité.

---

# 4. Cycle d'exécution

Un Application Service suit le cycle suivant :

```text
Entrée
   ↓
Validation applicative
   ↓
Chargement des agrégats
   ↓
Exécution du cas d'usage
   ↓
Invocation des Business Engines
   ↓
Persistance
   ↓
Publication des événements
   ↓
Retour du résultat
```

---

# 5. Dépendances

Les Application Services peuvent dépendre de :

* Repositories ;
* Unit of Work ;
* Business Engines ;
* Command Handlers ;
* Query Handlers.

Ils ne dépendent jamais des interfaces utilisateur.

---

# 6. Gestion des erreurs

Les erreurs sont propagées sous une forme standardisée.

Les services ne masquent jamais une erreur métier.

---

# 7. Transactions

Les transactions sont limitées au périmètre du cas d'usage.

Chaque transaction doit être :

* atomique ;
* cohérente ;
* la plus courte possible.

---

# 8. Testabilité

Chaque service doit pouvoir être testé indépendamment grâce à l'injection de dépendances et à l'utilisation d'interfaces.

---

# 9. Invariants

Les Application Services respectent toujours les règles suivantes :

* aucune logique métier ;
* un seul cas d'usage par service ;
* orchestration uniquement ;
* dépendances injectées ;
* indépendance de l'infrastructure.

---

# 10. Résumé

Les Application Services constituent la couche d'orchestration de Project Rebuild. Ils exécutent les cas d'usage en coordonnant les composants du système tout en laissant l'ensemble des décisions métier au Domaine et aux Business Engines.
