# AI Context Management

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la gestion du contexte utilisé par l'Intelligence Artificielle de Project Rebuild.

Le contexte permet au Coach IA de produire des réponses pertinentes tout en respectant les limites d'accès aux données.

---

# 2. Principes

La gestion du contexte respecte :

* minimisation des données ;
* pertinence ;
* confidentialité ;
* contrôle ;
* traçabilité.

---

# 3. Types de contexte

Le système distingue plusieurs niveaux.

---

# 3.1 User Context

Informations liées à l'utilisateur :

* objectifs ;
* préférences ;
* historique autorisé ;
* progression.

---

# 3.2 Domain Context

Informations issues du système métier :

* résultats des Engines ;
* événements ;
* états validés.

---

# 3.3 Conversation Context

Informations nécessaires à une interaction actuelle :

* sujet discuté ;
* historique récent ;
* intention utilisateur.

---

# 4. Source de vérité

Le contexte IA n'est jamais une source de vérité.

Il est une représentation temporaire permettant au modèle IA d'interpréter les informations disponibles.

La source officielle reste :

```text id="v3q9df"
Domain
  ↓
Engines
  ↓
Database
```

---

# 5. Construction du contexte

Le contexte est construit par le système.

L'utilisateur ne transmet pas directement toutes les données internes au modèle.

Flux :

```text id="j8f4pk"
Données système
      ↓
Filtrage
      ↓
Sélection du contexte utile
      ↓
IA
```

---

# 6. Confidentialité

Le système doit contrôler :

* quelles données sont accessibles ;
* combien de temps elles sont conservées ;
* dans quel objectif elles sont utilisées.

---

# 7. Taille du contexte

Le contexte doit rester :

* pertinent ;
* limité ;
* optimisé.

L'objectif n'est pas de transmettre toutes les informations disponibles mais uniquement celles nécessaires.

---

# 8. Mise à jour

Le contexte peut évoluer selon :

* nouvelles actions utilisateur ;
* nouveaux événements métier ;
* changements de progression.

---

# 9. Sécurité

Le système doit empêcher :

* accès non autorisé ;
* exposition de données privées ;
* utilisation hors contexte.

---

# 10. Invariants

La gestion du contexte garantit :

* données contrôlées ;
* source de vérité externe à l'IA ;
* confidentialité ;
* pertinence ;
* traçabilité.

---

# 11. Résumé

La gestion du contexte permet au Coach IA de comprendre l'utilisateur sans devenir propriétaire de ses données. Elle garantit un équilibre entre personnalisation, sécurité et fiabilité.
