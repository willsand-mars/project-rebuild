# AI Prompt Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'architecture des prompts utilisés par l'Intelligence Artificielle de Project Rebuild.

L'objectif est de garantir des interactions cohérentes, contrôlées et alignées avec la philosophie du produit.

Les prompts ne constituent jamais une source de logique métier.

Ils définissent uniquement la manière dont l'IA interprète et communique les informations validées.

---

# 2. Principes

L'architecture des prompts respecte :

* séparation données / instructions ;
* contrôle du comportement IA ;
* cohérence des réponses ;
* réutilisabilité ;
* évolution maîtrisée.

---

# 3. Structure générale

Un prompt IA est composé de plusieurs couches :

```text
System Instructions
        ↓
Product Rules
        ↓
User Context
        ↓
Domain Results
        ↓
Conversation Context
        ↓
User Request
        ↓
AI Response
```

---

# 4. System Instructions

Les instructions système définissent :

* rôle du Coach IA ;
* limites ;
* comportement attendu ;
* principes de communication.

Elles sont stables et contrôlées par l'équipe produit.

---

# 5. Product Rules

Cette couche rappelle à l'IA :

* la philosophie Project Rebuild ;
* les principes d'accompagnement ;
* les limites métier.

Elle ne contient jamais de calculs.

---

# 6. Domain Results

Les résultats provenant des Engines sont injectés comme données de référence.

Exemples :

* évolution du Rebuild Index ;
* progression utilisateur ;
* événements récents ;
* accomplissements.

L'IA interprète ces résultats mais ne les modifie pas.

---

# 7. User Context

Le contexte utilisateur permet une communication adaptée.

Il peut inclure :

* objectifs ;
* préférences ;
* historique autorisé ;
* style de communication préféré.

---

# 8. Conversation Context

Cette couche permet au Coach IA de maintenir une continuité dans une interaction.

Elle contient uniquement :

* éléments nécessaires ;
* informations pertinentes ;
* contexte récent.

---

# 9. Types de prompts

L'architecture distingue plusieurs catégories.

---

## Analyse

Objectif :

Expliquer une situation ou une évolution.

---

## Motivation

Objectif :

Renforcer l'engagement utilisateur.

---

## Explication

Objectif :

Rendre une donnée complexe compréhensible.

---

## Réflexion

Objectif :

Aider l'utilisateur à analyser son comportement.

---

# 10. Contraintes

Les prompts ne doivent jamais :

* demander à l'IA de calculer des résultats métier ;
* contourner les Engines ;
* inventer des données ;
* prendre des décisions critiques.

---

# 11. Versionnement

Les prompts doivent être :

* versionnés ;
* testables ;
* documentés.

Une modification importante doit pouvoir être analysée.

---

# 12. Tests

Les prompts doivent être évalués selon :

* précision ;
* cohérence ;
* respect des limites ;
* qualité des réponses.

---

# 13. Invariants

L'architecture garantit :

* prompts contrôlés ;
* données validées ;
* comportement cohérent ;
* absence de logique métier dans l'IA.

---

# 14. Résumé

L'architecture des prompts permet à Project Rebuild d'utiliser l'IA comme une couche intelligente d'accompagnement tout en maintenant une séparation stricte entre intelligence artificielle, logique métier et données officielles.
