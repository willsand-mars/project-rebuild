# Coach Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Coach Engine** est responsable de la préparation des informations destinées au Coach IA.

Il constitue l'unique point d'entrée métier entre les Engines et le système d'intelligence artificielle.

Le Coach Engine ne génère jamais lui-même les réponses destinées à l'utilisateur.

Son rôle est de produire un contexte métier fiable, cohérent et explicable.

---

# 2. Responsabilités

Le Coach Engine est responsable de :

* agréger les informations pertinentes ;
* sélectionner les événements significatifs ;
* produire un contexte métier ;
* expliquer les facteurs influents ;
* publier les événements liés à la préparation du coaching.

Il n'est jamais responsable de :

* inventer des informations ;
* modifier les données métier ;
* recalculer les Engines ;
* prendre des décisions à la place de l'IA.

---

# 3. Entrées

Le moteur peut consommer les rapports produits par :

* Rebuild Engine ;
* XP Engine ;
* Level Engine ;
* Mission Engine ;
* Habit Engine ;
* Streak Engine ;
* Badge Engine ;
* Achievement Engine ;
* Nutrition Engine ;
* Body Engine ;
* Health Engine.

Il utilise uniquement les résultats publiés.

---

# 4. Contexte produit

Le Coach Engine construit un **Coach Context** comprenant notamment :

* état actuel de progression ;
* principales évolutions ;
* missions en cours ;
* habitudes récentes ;
* progression globale ;
* événements significatifs ;
* niveau de confiance des analyses.

Ce contexte est exclusivement factuel.

---

# 5. Principes métier

## Aucune invention

Le moteur ne crée jamais d'information absente du domaine.

---

## Transparence

Toutes les informations du contexte doivent être traçables.

---

## Explicabilité

Chaque élément transmis au Coach IA doit pouvoir être justifié.

---

## Neutralité

Le moteur transmet des faits.

L'interprétation appartient exclusivement au Coach IA.

---

# 6. Sorties

Le moteur produit un **Coach Context Report** contenant notamment :

* résumé métier ;
* événements majeurs ;
* indicateurs utiles ;
* niveau de confiance ;
* horodatage ;
* version des règles.

Ce rapport est immuable.

---

# 7. Interactions

Le Coach Engine est consommé uniquement par la couche IA.

Aucun autre Engine ne dépend de lui pour ses calculs.

Il constitue une frontière entre le domaine métier et l'intelligence artificielle.

---

# 8. Contraintes

Le moteur garantit :

* aucune donnée inventée ;
* aucune modification des données sources ;
* contexte reproductible ;
* contexte explicable ;
* indépendance du modèle d'IA utilisé.

---

# 9. Événements publiés

Le moteur peut publier :

* CoachContextPrepared
* CoachingDataUpdated
* CoachingSummaryGenerated

Ces événements décrivent exclusivement la préparation du contexte métier.

---

# 10. Invariants

Le Coach Engine respecte les règles suivantes :

* aucune logique d'intelligence artificielle ;
* aucune génération de texte ;
* uniquement des faits métier ;
* aucune dépendance à un fournisseur d'IA ;
* aucune dépendance à l'interface utilisateur.

---

# 11. Dépendances

Le moteur dépend uniquement :

* des rapports des autres Engines ;
* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

Il ne dépend d'aucune technologie d'IA.

---

# 12. Résumé

Le Coach Engine est la passerelle métier entre Project Rebuild et le Coach IA. Il agrège les résultats produits par les différents Engines afin de construire un contexte fiable, déterministe et explicable, garantissant que l'intelligence artificielle interprète uniquement des faits validés par le domaine, sans jamais accéder directement aux données brutes.
