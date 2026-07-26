# Analytics Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Analytics Engine** est responsable de la production des indicateurs analytiques de Project Rebuild.

Il transforme les événements métier en métriques permettant d'évaluer la progression des utilisateurs, le fonctionnement du produit et l'efficacité des mécanismes métier.

Son objectif est analytique, jamais opérationnel.

---

# 2. Responsabilités

Le Analytics Engine est responsable de :

* agréger les événements métier ;
* produire des indicateurs ;
* calculer des tendances ;
* préparer les données destinées aux tableaux de bord ;
* publier les résultats analytiques.

Il n'est jamais responsable de :

* modifier les données métier ;
* attribuer des récompenses ;
* influencer les décisions des autres Engines ;
* envoyer des notifications.

---

# 3. Entrées

Le moteur consomme les événements publiés par l'ensemble des Business Engines.

Exemples :

* XPGained
* LevelReached
* MissionCompleted
* HabitCompleted
* StreakBroken
* BadgeUnlocked
* AchievementUnlocked
* RebuildIndexCalculated

---

# 4. Analyses produites

Le moteur peut produire notamment :

## Progression

* évolution moyenne du RBI ;
* évolution de l'XP ;
* progression des niveaux.

---

## Engagement

* fréquence des connexions ;
* missions réalisées ;
* habitudes validées ;
* stabilité des séries.

---

## Santé

* évolution des indicateurs de santé ;
* évolution corporelle ;
* adhérence nutritionnelle.

---

## Produit

* utilisation des fonctionnalités ;
* répartition des missions ;
* déblocage des badges ;
* obtention des succès.

Les indicateurs exacts pourront évoluer sans modifier les responsabilités du moteur.

---

# 5. Principes métier

## Lecture seule

Le moteur n'altère jamais les données du domaine.

---

## Agrégation

Les analyses sont produites à partir d'événements validés.

---

## Reproductibilité

Les mêmes événements conduisent toujours aux mêmes indicateurs.

---

## Traçabilité

Chaque indicateur peut être relié à ses événements d'origine.

---

# 6. Sorties

Le moteur produit un **Analytics Report** contenant notamment :

* indicateurs calculés ;
* période analysée ;
* niveau de confiance ;
* version des règles ;
* horodatage.

Le rapport est immuable.

---

# 7. Interactions

Les résultats peuvent être consommés par :

* tableaux de bord ;
* outils de supervision ;
* Coach Engine ;
* futurs moteurs d'analyse stratégique.

Le Analytics Engine n'influence jamais les autres Business Engines.

---

# 8. Contraintes

Le moteur garantit :

* lecture seule ;
* historique complet ;
* indépendance technologique ;
* calcul déterministe.

---

# 9. Événements publiés

Le moteur peut publier :

* AnalyticsReportGenerated
* AnalyticsSnapshotCreated
* AnalyticsTrendDetected

Ces événements décrivent uniquement la disponibilité de nouvelles analyses.

---

# 10. Invariants

Le Analytics Engine respecte les règles suivantes :

* aucune modification du domaine ;
* aucune logique d'interface ;
* aucune dépendance au stockage ;
* uniquement des données validées ;
* analyses entièrement reproductibles.

---

# 11. Dépendances

Le moteur dépend uniquement :

* des Domain Events ;
* des Entités ;
* des Value Objects ;
* des Domain Services.

---

# 12. Résumé

Le Analytics Engine constitue la couche d'observation de Project Rebuild. Il transforme les événements du domaine en indicateurs fiables, reproductibles et explicables, permettant d'analyser la progression des utilisateurs et le comportement du système sans jamais intervenir dans les décisions métier.
