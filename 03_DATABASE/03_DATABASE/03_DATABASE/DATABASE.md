# Database Principles

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les principes fondamentaux de la persistance des données de Project Rebuild.

Il sert de référence pour toute implémentation future de la base de données.

---

# 2. Source de vérité

La source de vérité du système reste le Domaine.

La base de données ne fait que conserver son état.

Aucune décision métier n'est prise au niveau du stockage.

---

# 3. Modèle de persistance

Le modèle de persistance doit permettre :

* la reconstruction complète du domaine ;
* l'historisation des évolutions ;
* la traçabilité des décisions ;
* la reproductibilité des calculs des Engines.

---

# 4. Séparation Lecture / Écriture

Le modèle distingue clairement :

## Modèle d'écriture

Optimisé pour :

* l'intégrité ;
* la cohérence ;
* les transactions.

---

## Modèle de lecture

Optimisé pour :

* les tableaux de bord ;
* les statistiques ;
* les recherches ;
* les interfaces utilisateur.

Les projections de lecture peuvent être reconstruites à partir des données d'origine.

---

# 5. Identifiants

Chaque agrégat possède un identifiant unique.

Les identifiants sont :

* immuables ;
* opaques ;
* indépendants de la technologie.

Ils ne véhiculent aucune information métier.

---

# 6. Horodatage

Les objets persistés doivent enregistrer au minimum :

* date de création ;
* date de dernière modification.

Lorsque nécessaire :

* date d'archivage ;
* date de suppression logique.

Tous les horodatages sont stockés en UTC.

---

# 7. Transactions

Les écritures doivent garantir :

* l'atomicité ;
* la cohérence ;
* l'isolation ;
* la durabilité.

Les transactions doivent rester les plus courtes possibles.

---

# 8. Immutabilité

Les événements du domaine sont immuables.

Les journaux historiques ne sont jamais modifiés.

Toute correction produit un nouvel événement.

---

# 9. Versionnement

Les objets persistés peuvent être versionnés.

Chaque évolution importante conserve sa version métier afin d'assurer la compatibilité des calculs futurs.

---

# 10. Intégrité

Le stockage garantit :

* l'unicité des identifiants ;
* la cohérence des relations ;
* la validité des références ;
* l'absence de duplication métier.

---

# 11. Performance

Les optimisations de performance ne doivent jamais modifier la logique métier.

Les index, caches ou projections sont considérés comme des optimisations d'infrastructure.

---

# 12. Sécurité

La couche de persistance doit permettre :

* la protection des données ;
* la journalisation des opérations ;
* la récupération après incident ;
* la sauvegarde des données.

Les mécanismes techniques restent indépendants de cette spécification.

---

# 13. Évolutivité

Le modèle doit permettre :

* l'ajout de nouveaux agrégats ;
* l'ajout de nouvelles projections ;
* l'évolution des schémas ;
* les migrations sans perte de données.

---

# 14. Invariants

Le modèle de persistance respecte toujours les règles suivantes :

* aucune logique métier dans la base ;
* aucune dépendance au SGBD ;
* aucune dépendance au Backend ;
* aucune dépendance au Frontend ;
* aucune dépendance à l'IA ;
* événements immuables ;
* données traçables ;
* données reproductibles.

---

# 15. Résumé

La base de données de Project Rebuild est une représentation persistante du domaine, conçue pour garantir l'intégrité, la traçabilité, l'évolutivité et la reproductibilité des données. Elle reste totalement indépendante des choix technologiques et ne contient jamais de logique métier.
