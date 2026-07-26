# Health Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Health Engine** est responsable de l'analyse globale des indicateurs de santé utilisés par Project Rebuild.

Son rôle est d'agréger les données de santé validées afin de produire des indicateurs métier fiables, exploitables par les autres Engines.

Le Health Engine n'est pas un moteur de diagnostic médical.

Il ne remplace jamais un professionnel de santé.

---

# 2. Responsabilités

Le Health Engine est responsable de :

* consolider les indicateurs de santé ;
* analyser leur évolution ;
* détecter les variations significatives ;
* produire des indicateurs synthétiques ;
* publier les événements métier associés.

Il n'est jamais responsable de :

* établir un diagnostic médical ;
* recommander un traitement ;
* prescrire une activité physique ;
* attribuer de l'XP ;
* générer des notifications.

---

# 3. Entrées

Le moteur consomme uniquement les données validées du domaine.

Exemples :

* sommeil ;
* fréquence cardiaque ;
* récupération ;
* niveau d'énergie ;
* fatigue déclarée ;
* autres indicateurs de santé approuvés par le domaine.

Toutes les données sont considérées comme préalablement validées.

---

# 4. Principes métier

## Vision globale

Le moteur évalue la santé comme un ensemble cohérent.

Aucun indicateur isolé ne suffit à produire une conclusion globale.

---

## Tendance avant instantané

Les analyses portent sur une période d'observation.

Une valeur exceptionnelle ne suffit jamais à caractériser une évolution.

---

## Neutralité

Le moteur décrit les observations.

Il ne porte aucun jugement.

---

## Explicabilité

Chaque résultat doit pouvoir être relié aux données ayant conduit à son calcul.

---

# 5. Analyses produites

Le moteur peut produire notamment :

* évolution du sommeil ;
* évolution de la récupération ;
* stabilité énergétique ;
* évolution de la fatigue ;
* cohérence globale des indicateurs.

Le détail algorithmique est défini séparément.

---

# 6. Sorties

Le moteur produit un **Health Report** contenant notamment :

* période analysée ;
* indicateurs calculés ;
* principales évolutions ;
* niveau de confiance ;
* version des règles métier ;
* horodatage.

Le rapport est immuable.

---

# 7. Interactions

Les résultats peuvent être consommés par :

* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine ;
* Achievement Engine.

Le moteur reste indépendant des autres Engines.

---

# 8. Contraintes

Le moteur garantit :

* calcul reproductible ;
* historique cohérent ;
* indépendance technologique ;
* explicabilité des résultats.

---

# 9. Événements publiés

Le moteur peut publier :

* HealthAnalysisCompleted
* HealthTrendChanged
* RecoveryImproved
* RecoveryDeclined
* SleepTrendChanged

Ces événements représentent uniquement des faits métier.

---

# 10. Invariants

Le Health Engine respecte les règles suivantes :

* uniquement des données validées ;
* aucune modification des données sources ;
* aucun diagnostic médical ;
* aucune recommandation médicale ;
* aucune dépendance à l'interface utilisateur ;
* aucune dépendance à l'infrastructure.

---

# 11. Dépendances

Le moteur dépend uniquement :

* des Entités ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events.

---

# 12. Résumé

Le Health Engine fournit une vision métier de l'évolution des indicateurs de santé de l'utilisateur. Il produit des analyses déterministes, explicables et indépendantes de toute technologie afin d'alimenter le Rebuild Engine, le Coach Engine et les moteurs d'analyse.
