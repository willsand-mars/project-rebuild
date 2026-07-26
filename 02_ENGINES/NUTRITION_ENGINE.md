# Nutrition Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Nutrition Engine** est responsable de l'évaluation de l'adhérence nutritionnelle de l'utilisateur.

Son objectif n'est pas de compter les calories ni de juger les choix alimentaires, mais de mesurer dans quelle mesure les comportements observés sont cohérents avec le plan nutritionnel défini dans le domaine.

Le moteur évalue des tendances, jamais un repas isolé.

---

# 2. Responsabilités

Le Nutrition Engine est responsable de :

* analyser les données nutritionnelles validées ;
* mesurer l'adhérence aux objectifs ;
* calculer des indicateurs nutritionnels ;
* détecter les évolutions significatives ;
* publier les événements métier associés.

Il n'est jamais responsable de :

* créer un plan alimentaire ;
* recommander un régime ;
* attribuer de l'XP ;
* calculer le RBI ;
* envoyer des notifications.

---

# 3. Entrées

Le moteur consomme uniquement :

* les journaux alimentaires validés ;
* les objectifs nutritionnels du domaine ;
* les événements métier liés à la nutrition.

Toutes les données sont supposées validées avant leur traitement.

---

# 4. Principes métier

## Cohérence avant perfection

Une alimentation globalement cohérente est davantage valorisée qu'une journée parfaite suivie d'abandons.

---

## Tendance avant instantané

Le moteur analyse une période d'observation.

Une journée exceptionnelle ne modifie pas seule l'évaluation globale.

---

## Neutralité

Aucun aliment n'est considéré comme "bon" ou "mauvais".

Seule la cohérence avec les objectifs est évaluée.

---

## Explicabilité

Chaque résultat doit pouvoir être justifié par des faits métier.

---

# 5. Analyses produites

Le moteur peut produire notamment :

* niveau d'adhérence ;
* stabilité alimentaire ;
* fréquence des écarts ;
* cohérence nutritionnelle ;
* qualité globale de la période observée.

Les algorithmes restent indépendants de toute technologie.

---

# 6. Sorties

Le moteur produit un **Nutrition Report** contenant :

* période analysée ;
* indicateurs calculés ;
* niveau d'adhérence ;
* principaux facteurs d'influence ;
* niveau de confiance ;
* horodatage ;
* version des règles métier.

Le rapport est immuable.

---

# 7. Interactions

Le Nutrition Engine publie des événements pouvant être consommés par :

* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine ;
* Badge Engine ;
* Achievement Engine.

Le moteur ne dépend d'aucun autre Engine.

---

# 8. Contraintes

Le moteur garantit :

* calcul reproductible ;
* indépendance des interfaces ;
* historique cohérent ;
* explicabilité des résultats.

---

# 9. Événements publiés

Le moteur peut publier :

* NutritionAnalysisCompleted
* NutritionAdherenceImproved
* NutritionAdherenceDeclined
* NutritionTrendChanged

---

# 10. Invariants

* les calculs reposent uniquement sur des données validées ;
* les résultats sont déterministes ;
* aucune recommandation n'est produite ;
* aucune donnée n'est modifiée ;
* le moteur reste indépendant de la couche technique.

---

# 11. Dépendances

Le Nutrition Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 12. Résumé

Le Nutrition Engine mesure l'adhérence nutritionnelle de l'utilisateur à partir des données du domaine. Il fournit une vision fiable, explicable et orientée tendances de la cohérence alimentaire, servant de fondation au Rebuild Engine, au Coach IA et aux moteurs d'analyse.
