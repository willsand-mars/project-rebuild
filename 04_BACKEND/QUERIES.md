# Queries

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Les **Queries** représentent les demandes de consultation des données.

Une Query permet d'obtenir des informations sans modifier l'état du système.

Elle appartient au modèle de lecture.

---

# 2. Responsabilités

Une Query est responsable de :

* exprimer un besoin de lecture ;
* transporter les paramètres de recherche ;
* retourner une représentation des données.

Elle n'est jamais responsable de :

* modifier le domaine ;
* déclencher des traitements métier ;
* produire des événements métier.

---

# 3. Principes

Chaque Query respecte les principes suivants :

* lecture seule ;
* déterministe ;
* immuable ;
* indépendante de l'interface utilisateur.

---

# 4. Cycle de vie

Une Query suit le processus suivant :

```text
Client
    ↓
API
    ↓
Validation
    ↓
Query Handler
    ↓
Projection
    ↓
Résultat
```

---

# 5. Source des données

Une Query peut lire :

* les agrégats persistés ;
* les projections de lecture ;
* les vues analytiques.

Elle ne modifie jamais ces données.

---

# 6. Optimisation

Les modèles de lecture peuvent être optimisés indépendamment du modèle d'écriture.

Ces optimisations restent transparentes pour les consommateurs.

---

# 7. Pagination

Les résultats volumineux doivent pouvoir être :

* paginés ;
* triés ;
* filtrés.

Les critères restent indépendants de la technologie utilisée.

---

# 8. Traçabilité

Chaque Query peut être corrélée à :

* un utilisateur ;
* un identifiant de requête ;
* un horodatage.

---

# 9. Invariants

Les Queries respectent toujours les règles suivantes :

* aucune modification des données ;
* aucune logique métier ;
* lecture uniquement ;
* indépendance du stockage.

---

# 10. Résumé

Les Queries constituent le modèle de lecture de Project Rebuild. Elles permettent d'accéder aux informations de manière optimisée, déterministe et sans impact sur le Domaine ni sur les Business Engines.
