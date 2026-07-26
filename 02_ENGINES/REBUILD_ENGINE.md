# 02_ENGINES/REBUILD_ENGINE.md

# Rebuild Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine
**Domaine :** Core Decision System

---

# 1. Objectif

Le **Rebuild Engine** est le moteur décisionnel principal de Project Rebuild.

Sa responsabilité est de transformer l'ensemble des informations du domaine en une mesure unique représentant l'état global de progression de l'utilisateur.

Cette mesure est appelée :

> **Rebuild Index (RBI)**

Le RBI n'est ni une note, ni un score de performance.

Il représente l'état actuel de reconstruction de l'utilisateur au regard de son propre parcours.

Le Rebuild Engine ne formule jamais de recommandations.

Il produit uniquement une interprétation métier exploitable par les autres Engines.

---

# 2. Position dans l'architecture

```
Utilisateur

↓

Domain

↓

Rebuild Engine

↓

Autres Engines

↓

Coach IA

↓

Interface
```

Le Rebuild Engine constitue la source de vérité concernant l'état global de progression.

Tous les moteurs métiers peuvent le consulter.

Aucun moteur ne peut modifier directement son résultat.

---

# 3. Responsabilités

Le Rebuild Engine est responsable de :

* analyser les informations métier disponibles ;
* calculer le Rebuild Index ;
* détecter les évolutions positives ou négatives ;
* mesurer la stabilité de progression ;
* produire des indicateurs métier standardisés ;
* déclencher les événements liés aux changements significatifs.

Il n'est jamais responsable de :

* générer une interface utilisateur ;
* afficher des graphiques ;
* envoyer des notifications ;
* créer des missions ;
* proposer des conseils personnalisés.

---

# 4. Entrées

Le moteur ne collecte aucune donnée lui-même.

Il consomme uniquement les informations produites par le domaine.

Les entrées proviennent exclusivement des agrégats et des événements validés.

Exemples de catégories de données :

## Progression

* XP actuelle
* Niveau
* Historique d'évolution
* Badges obtenus
* Succès validés

---

## Habitudes

* missions terminées
* missions échouées
* fréquence
* continuité
* régularité

---

## Santé

* poids
* mensurations
* évolution corporelle
* indicateurs autorisés par le domaine

Le moteur reste indépendant des unités utilisées.

---

## Nutrition

* adhérence aux objectifs
* qualité globale des journées
* cohérence dans le temps

Le moteur n'analyse jamais un aliment individuellement.

---

## Activité

* entraînements
* activité quotidienne
* récupération
* repos

---

## Mental

* motivation déclarée
* humeur
* fatigue
* confiance
* perception personnelle

Le moteur ne réalise aucune analyse psychologique.

Il utilise uniquement les informations déjà validées par le domaine.

---

## Historique

Le moteur travaille toujours sur une période.

Jamais sur une seule journée.

La fenêtre d'analyse est définie par la configuration métier.

---

# 5. Sorties

Le moteur produit un objet métier unique.

```
Rebuild Index Report
```

Il contient notamment :

* valeur du RBI
* tendance
* variation
* stabilité
* niveau de confiance
* principaux facteurs ayant influencé le résultat
* horodatage
* version de l'algorithme

Le rapport constitue une photographie métier.

Il est immuable après sa création.

---

# 6. Le Rebuild Index

Le RBI représente la reconstruction globale.

Il ne cherche pas à mesurer :

* la force ;
* le poids ;
* les calories ;
* la masse musculaire.

Il mesure la cohérence entre les comportements observés et les objectifs du domaine.

Le RBI est donc un indicateur synthétique de progression.

---

# 7. Principes de calcul

Le détail mathématique n'est volontairement pas défini dans ce document.

Le moteur doit néanmoins respecter les principes suivants.

## 7.1 Progression avant performance

Une légère amélioration régulière est toujours mieux valorisée qu'une performance exceptionnelle isolée.

---

## 7.2 Discipline avant motivation

Les comportements répétés ont davantage d'impact que les déclarations d'intention.

---

## 7.3 Tendance avant instantané

Le moteur privilégie les évolutions dans le temps.

Une mauvaise journée ne doit pas provoquer une chute brutale.

---

## 7.4 Résilience

Après une période difficile, une reprise régulière doit être reconnue rapidement.

Le moteur ne doit jamais enfermer l'utilisateur dans un état négatif.

---

## 7.5 Neutralité

Le moteur ne juge jamais.

Il décrit uniquement une évolution observée.

---

## 7.6 Explicabilité

Chaque variation importante du RBI doit pouvoir être expliquée.

Aucune décision ne doit être opaque.

---

# 8. Variations

Deux rapports successifs peuvent produire :

* amélioration
* stabilité
* légère baisse
* baisse importante

La variation doit être interprétable.

Elle ne représente jamais une sanction.

---

# 9. Niveau de confiance

Chaque résultat possède un niveau de confiance.

Exemples :

* faible
* moyen
* élevé

Ce niveau indique la qualité des données utilisées.

Un RBI obtenu avec peu d'informations reste valide mais moins représentatif.

---

# 10. Facteurs d'influence

Le moteur identifie les principaux facteurs ayant influencé le résultat.

Exemples :

* excellente régularité
* diminution des missions réalisées
* amélioration de la récupération
* augmentation de la cohérence nutritionnelle

Ces facteurs sont descriptifs.

Ils ne constituent jamais des recommandations.

---

# 11. Interactions avec les autres Engines

Le Rebuild Engine ne dépend d'aucun autre Engine métier.

Il constitue une base de calcul.

Les autres Engines peuvent consommer son résultat.

Exemples :

* Mission Engine
* XP Engine
* Badge Engine
* Achievement Engine
* Coach Engine
* Notification Engine
* Analytics Engine

Les dépendances sont unidirectionnelles.

```
Autres Engines

↓

consultent

↓

Rebuild Engine
```

Le Rebuild Engine ne déclenche jamais directement leurs traitements.

Il publie uniquement des événements.

---

# 12. Contraintes métier

Le moteur doit rester :

* déterministe ;
* reproductible ;
* testable ;
* explicable ;
* indépendant de l'interface.

Le résultat doit être identique pour des données identiques.

---

# 13. Gestion des données incomplètes

Le moteur doit pouvoir fonctionner même si certaines données sont absentes.

Dans ce cas :

* les données disponibles sont utilisées ;
* le niveau de confiance est ajusté ;
* aucune erreur métier n'est générée.

---

# 14. Versionnement

Le calcul du RBI est versionné.

Chaque rapport contient :

* version du moteur
* date de calcul
* paramètres métier utilisés

Cela garantit la traçabilité complète des résultats.

---

# 15. Événements publiés

Lorsque certaines conditions métier sont remplies, le moteur publie des événements du domaine.

Exemples :

* RebuildIndexCalculated
* RebuildIndexImproved
* RebuildIndexDeclined
* RebuildTrendChanged
* RebuildStabilityChanged
* RebuildConfidenceChanged

Le moteur publie uniquement des faits métier.

Il ne connaît jamais les consommateurs de ces événements.

---

# 16. Invariants

Le moteur doit toujours respecter les règles suivantes.

* Le RBI est calculé uniquement à partir des données du domaine.
* Le RBI ne dépend jamais de l'interface utilisateur.
* Le RBI est explicable.
* Le RBI est reproductible.
* Le RBI est immuable une fois publié.
* Le moteur ne formule jamais de recommandations.
* Le moteur ne crée jamais de missions.
* Le moteur ne modifie jamais les entités métier.
* Les traitements sont indépendants de toute technologie.
* Les événements publiés représentent exclusivement des faits métier.

---

# 17. Dépendances

Le Rebuild Engine dépend uniquement :

* des Entités du domaine ;
* des Value Objects ;
* des Domain Events ;
* des Services métier validés.

Il ne dépend :

* ni du backend ;
* ni de la base de données ;
* ni de l'interface ;
* ni de l'intelligence artificielle ;
* ni d'un framework.

---

# 18. Résumé

Le Rebuild Engine constitue le cœur décisionnel de Project Rebuild.

Il transforme les informations du domaine en une représentation cohérente de la progression globale de l'utilisateur grâce au Rebuild Index (RBI).

Il ne prend aucune décision de présentation, ne fournit aucune recommandation et ne modifie jamais l'état du domaine. Sa mission est de produire une évaluation métier fiable, explicable, déterministe et versionnée, servant de fondation à l'ensemble des autres Engines et au Coach IA.
