# Validation Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de validation de Project Rebuild.

La validation garantit que les données reçues par le système respectent les contraintes nécessaires avant leur traitement.

Elle distingue clairement :

* validation technique ;
* validation applicative ;
* validation métier.

---

# 2. Principes

La validation respecte les principes suivants :

* chaque couche valide uniquement son périmètre ;
* aucune duplication inutile de règles ;
* aucune règle métier dans les couches externes ;
* messages d'erreur explicites.

---

# 3. Validation technique

La validation technique vérifie :

* présence des champs obligatoires ;
* formats ;
* types ;
* tailles ;
* structures.

Elle intervient avant l'exécution d'un cas d'usage.

---

# 4. Validation applicative

La validation applicative vérifie :

* cohérence de la requête ;
* existence des ressources nécessaires ;
* autorisations nécessaires ;
* préconditions du cas d'usage.

---

# 5. Validation métier

La validation métier appartient exclusivement au Domaine.

Elle vérifie :

* invariants ;
* règles métier ;
* cohérence des agrégats ;
* décisions des Business Engines.

---

# 6. Flux de validation

```text id="6xk0n1"
Entrée utilisateur
        ↓
Validation technique
        ↓
Validation applicative
        ↓
Validation métier
        ↓
Exécution
```

---

# 7. Responsabilités

Chaque couche reste responsable de ses propres validations.

Aucune couche ne doit contourner une validation appartenant à une autre.

---

# 8. Messages d'erreur

Les erreurs de validation doivent être :

* précises ;
* compréhensibles ;
* actionnables.

Elles doivent permettre à l'utilisateur ou au système appelant de comprendre le problème.

---

# 9. Testabilité

Les validations doivent pouvoir être testées indépendamment :

* tests techniques ;
* tests applicatifs ;
* tests métier.

---

# 10. Invariants

Le système respecte toujours :

* validation avant traitement ;
* règles métier uniquement dans le Domaine ;
* aucune confiance dans les entrées externes ;
* cohérence permanente des données.

---

# 11. Résumé

La stratégie de validation de Project Rebuild garantit que chaque donnée est contrôlée au bon niveau de responsabilité. Elle protège le Domaine tout en maintenant une architecture claire, testable et évolutive.
