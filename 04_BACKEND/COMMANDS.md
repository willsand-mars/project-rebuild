# Commands

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Les **Commands** représentent les intentions de modification du système.

Une Command exprime qu'un utilisateur ou un service souhaite effectuer une action susceptible de modifier l'état du domaine.

Elle décrit une intention.

Elle ne contient aucune logique métier.

---

# 2. Responsabilités

Une Command est responsable de :

* transporter les données nécessaires au cas d'usage ;
* représenter une intention métier ;
* être validée avant son exécution.

Une Command n'est jamais responsable de :

* exécuter une action ;
* modifier la base de données ;
* prendre une décision métier.

---

# 3. Principes

Chaque Command respecte les principes suivants :

* immuable ;
* auto-descriptive ;
* fortement typée ;
* indépendante de l'interface utilisateur.

---

# 4. Cycle de vie

Une Command suit le processus suivant :

```text
Client
    ↓
API
    ↓
Validation applicative
    ↓
Command Handler
    ↓
Application Service
    ↓
Domain
```

---

# 5. Validation

Une Command est validée avant son traitement.

La validation porte uniquement sur :

* la structure ;
* les formats ;
* les champs obligatoires.

Les règles métier restent dans le Domaine.

---

# 6. Résultat

Une Command ne retourne jamais directement les données du domaine.

Elle retourne uniquement le résultat du cas d'usage :

* succès ;
* échec ;
* identifiant créé ;
* erreur standardisée.

---

# 7. Idempotence

Lorsqu'un cas d'usage l'exige, une Command doit pouvoir être rejouée sans produire d'effet secondaire.

---

# 8. Traçabilité

Chaque exécution de Command peut être corrélée à :

* un utilisateur ;
* une session ;
* un identifiant de corrélation ;
* un horodatage.

---

# 9. Invariants

Les Commands respectent toujours les règles suivantes :

* immuables ;
* aucune logique métier ;
* aucune dépendance à la base de données ;
* aucune dépendance au Frontend.

---

# 10. Résumé

Les Commands représentent les intentions de modification du système. Elles transportent les informations nécessaires à un cas d'usage sans contenir de logique métier et constituent le point d'entrée du modèle d'écriture de Project Rebuild.
