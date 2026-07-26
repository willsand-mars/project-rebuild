# Database Constraints

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les contraintes garantissant l'intégrité des données persistées.

Les contraintes assurent la cohérence du stockage mais ne remplacent jamais les validations métier réalisées par le Domaine et les Business Engines.

---

# 2. Principes

Les contraintes doivent garantir :

* intégrité ;
* cohérence ;
* unicité ;
* traçabilité.

Les validations métier restent en dehors de la base de données.

---

# 3. Contraintes d'identité

Chaque agrégat possède :

* un identifiant unique ;
* un identifiant immuable ;
* un identifiant non réutilisable.

Aucun identifiant ne peut être modifié après création.

---

# 4. Contraintes d'unicité

Les éléments devant être uniques sont protégés.

Exemples :

* identifiant utilisateur ;
* identifiant d'événement ;
* identifiant de transaction XP.

Les doublons sont interdits.

---

# 5. Contraintes référentielles

Toute référence doit :

* pointer vers une ressource existante ;
* respecter le cycle de vie des agrégats ;
* rester valide dans le temps.

Les références orphelines sont interdites.

---

# 6. Contraintes temporelles

Les horodatages doivent :

* être enregistrés en UTC ;
* rester cohérents chronologiquement ;
* permettre l'historisation complète.

---

# 7. Contraintes d'immuabilité

Les données suivantes sont immuables après création :

* Domain Events ;
* Audit Logs ;
* XP Transactions ;
* historiques.

Toute correction crée un nouvel enregistrement.

---

# 8. Contraintes de suppression

La suppression physique est exceptionnelle.

Par défaut :

* archivage ;
* suppression logique ;
* conservation de l'historique.

Les règles détaillées sont définies dans **SOFT_DELETE.md**.

---

# 9. Contraintes de version

Chaque objet versionné doit conserver :

* sa version métier ;
* sa date de création ;
* son historique d'évolution.

---

# 10. Contraintes de cohérence

Les écritures doivent garantir :

* atomicité ;
* cohérence ;
* isolation ;
* durabilité.

Les transactions restent limitées au périmètre nécessaire.

---

# 11. Contraintes de sécurité

Les données doivent pouvoir être :

* sauvegardées ;
* restaurées ;
* auditées.

Les mécanismes techniques restent indépendants de cette spécification.

---

# 12. Invariants

Les contraintes respectent toujours les règles suivantes :

* aucune logique métier ;
* aucune dépendance au SGBD ;
* aucune dépendance au Backend ;
* cohérence permanente des données ;
* traçabilité complète.

---

# 13. Résumé

Les contraintes de persistance garantissent que les données de Project Rebuild demeurent cohérentes, fiables et historisées, tout en laissant l'ensemble des décisions métier au Domaine et aux Business Engines.
