# Data Versioning

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de versionnement des données persistées dans Project Rebuild.

Le versionnement garantit la compatibilité des évolutions du système, la reproductibilité des calculs des Engines et la traçabilité complète des modifications.

---

# 2. Principes

Le versionnement permet de :

* préserver la compatibilité des données ;
* assurer la reproductibilité des calculs ;
* faciliter les migrations ;
* conserver un historique fiable.

Le versionnement n'est jamais utilisé pour implémenter une logique métier.

---

# 3. Objets concernés

Les éléments pouvant être versionnés sont notamment :

* Entités ;
* Value Objects persistés ;
* Domain Events ;
* Engine Reports ;
* Snapshots ;
* Projections.

---

# 4. Version métier

Chaque objet versionné possède un identifiant de version.

Exemple conceptuel :

```text
Version 1
Version 2
Version 3
```

La version représente une évolution du modèle métier, indépendamment de la technologie de stockage.

---

# 5. Compatibilité

Toute nouvelle version doit définir sa stratégie de compatibilité :

* rétrocompatible ;
* nécessitant une migration ;
* nécessitant une reconstruction.

Cette décision est documentée lors de l'évolution du modèle.

---

# 6. Historique

Les anciennes versions restent traçables lorsque cela est nécessaire.

Une mise à jour ne doit jamais empêcher l'audit des versions précédentes.

---

# 7. Engine Reports

Les rapports générés par les Business Engines enregistrent :

* la version de l'Engine ;
* la version des règles métier ;
* la date de génération.

Cela garantit qu'un calcul peut être reproduit dans son contexte d'origine.

---

# 8. Domain Events

Les événements enregistrent leur propre version.

Une évolution de leur structure ne doit jamais invalider les événements historiques.

---

# 9. Évolution du schéma

Une évolution du modèle de données ne modifie jamais rétroactivement les décisions métier déjà enregistrées.

Les anciennes données conservent leur valeur historique.

---

# 10. Contraintes

Le versionnement garantit :

* traçabilité ;
* cohérence ;
* reproductibilité ;
* auditabilité.

---

# 11. Invariants

Le système respecte toujours les règles suivantes :

* aucune perte de version ;
* aucune modification silencieuse ;
* aucune dépendance à une technologie spécifique ;
* conservation des métadonnées de version.

---

# 12. Résumé

Le versionnement constitue un mécanisme fondamental de Project Rebuild. Il assure la stabilité des données, la compatibilité des évolutions et la reproductibilité des traitements métier sur le long terme.
