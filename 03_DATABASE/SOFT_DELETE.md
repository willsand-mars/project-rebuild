# Soft Delete Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de suppression des données de Project Rebuild.

Par défaut, les données ne sont jamais supprimées physiquement.

Le système privilégie l'archivage et la suppression logique afin de préserver la traçabilité, l'auditabilité et la cohérence du domaine.

---

# 2. Principes

La suppression logique permet de :

* conserver l'historique ;
* éviter les pertes accidentelles ;
* garantir la reproductibilité des calculs ;
* préserver les références métier.

La suppression physique constitue une opération exceptionnelle.

---

# 3. Suppression logique

Lorsqu'un agrégat est supprimé, il est marqué comme inactif.

Il reste présent dans la base de données.

Les informations suivantes sont conservées :

* date de suppression ;
* raison de la suppression ;
* version métier ;
* métadonnées d'audit.

---

# 4. Suppression physique

Une suppression physique n'est autorisée que dans les cas suivants :

* obligations réglementaires ;
* données temporaires prévues pour être purgées ;
* opérations d'administration documentées.

Elle doit rester exceptionnelle.

---

# 5. Effets métier

Une suppression logique :

* ne modifie pas l'historique ;
* ne supprime pas les Domain Events ;
* ne modifie pas les Engine Reports ;
* conserve les relations nécessaires à l'audit.

---

# 6. Visibilité

Les données supprimées logiquement sont exclues des traitements fonctionnels courants.

Elles restent accessibles uniquement :

* aux mécanismes d'administration ;
* aux outils d'audit ;
* aux processus de restauration autorisés.

---

# 7. Restauration

Une donnée supprimée logiquement peut être restaurée si les règles métier l'autorisent.

Toute restauration est historisée.

---

# 8. Contraintes

Le système garantit :

* aucune perte involontaire ;
* conservation des références historiques ;
* traçabilité des suppressions ;
* cohérence des agrégats.

---

# 9. Invariants

Les règles suivantes sont toujours respectées :

* les Domain Events ne sont jamais supprimés ;
* les Audit Logs restent immuables ;
* les historiques sont conservés ;
* aucune suppression silencieuse n'est autorisée.

---

# 10. Résumé

La stratégie de suppression de Project Rebuild privilégie la conservation des données afin de garantir l'intégrité historique du domaine. La suppression logique constitue le comportement par défaut, tandis que la suppression physique reste une exception strictement contrôlée.
