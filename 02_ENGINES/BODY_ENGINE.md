# Body Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Body Engine** est responsable de l'analyse de l'évolution corporelle de l'utilisateur.

Il transforme les mesures physiques validées en indicateurs de progression exploitables par le domaine.

Le moteur décrit les évolutions observées sans interprétation médicale.

---

# 2. Responsabilités

Le Body Engine est responsable de :

* analyser les mesures corporelles ;
* mesurer les évolutions dans le temps ;
* détecter les changements significatifs ;
* calculer des indicateurs de progression ;
* publier les événements métier.

Il n'est jamais responsable de :

* établir un diagnostic médical ;
* recommander un traitement ;
* attribuer de l'XP ;
* calculer le RBI ;
* envoyer des notifications.

---

# 3. Entrées

Le moteur consomme uniquement :

* poids ;
* mensurations ;
* composition corporelle (si disponible) ;
* photographies ou analyses déjà validées par le domaine ;
* historique des mesures.

---

# 4. Principes métier

## Évolution avant résultat

Le moteur privilégie les tendances plutôt que les valeurs absolues.

---

## Contexte personnel

Les analyses sont réalisées par rapport à l'historique de l'utilisateur.

Aucune comparaison entre utilisateurs n'est effectuée.

---

## Neutralité

Les changements corporels sont décrits objectivement.

Aucune valeur morale n'est associée aux résultats.

---

## Explicabilité

Chaque évolution significative doit être justifiable.

---

# 5. Analyses produites

Le moteur peut calculer notamment :

* évolution du poids ;
* évolution des mensurations ;
* stabilité corporelle ;
* rythme d'évolution ;
* cohérence avec les objectifs définis.

Les méthodes de calcul sont indépendantes de toute implémentation technique.

---

# 6. Sorties

Le moteur produit un **Body Report** contenant :

* période d'analyse ;
* indicateurs calculés ;
* principales évolutions observées ;
* niveau de confiance ;
* horodatage ;
* version des règles métier.

Le rapport est immuable.

---

# 7. Interactions

Le Body Engine publie des événements consommés notamment par :

* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine ;
* Achievement Engine.

---

# 8. Contraintes

Le moteur garantit :

* analyses déterministes ;
* indépendance technologique ;
* conservation de l'historique ;
* résultats explicables.

---

# 9. Événements publiés

Le moteur peut publier :

* BodyAnalysisCompleted
* BodyProgressDetected
* BodyPlateauDetected
* BodyTrendChanged

---

# 10. Invariants

* seules des données validées sont analysées ;
* aucune modification des mesures d'origine ;
* aucune interprétation médicale ;
* aucun accès direct à l'interface utilisateur ;
* aucune dépendance à l'infrastructure.

---

# 11. Dépendances

Le Body Engine dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 12. Résumé

Le Body Engine fournit une analyse métier de l'évolution corporelle de l'utilisateur. Il transforme les mesures physiques en indicateurs fiables, explicables et orientés tendances, sans établir de diagnostic ni produire de recommandations, afin d'alimenter les moteurs décisionnels de Project Rebuild.
