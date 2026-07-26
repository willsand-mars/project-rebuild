# 02_ENGINES/LEVEL_ENGINE.md

# Level Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Level Engine** est responsable de la détermination du niveau de progression d'un utilisateur à partir de son expérience (XP).

Le niveau représente une étape durable dans le parcours de reconstruction. Il matérialise la progression globale sans mesurer directement les performances physiques.

Le Level Engine ne calcule jamais l'XP ; il l'interprète.

---

# 2. Responsabilités

Le Level Engine est responsable de :

* déterminer le niveau courant ;
* détecter un changement de niveau ;
* calculer la progression vers le niveau suivant ;
* publier les événements liés au changement de niveau.

Il n'est jamais responsable de :

* attribuer de l'XP ;
* débloquer des badges ;
* créer des missions ;
* calculer le RBI ;
* envoyer des notifications.

---

# 3. Entrées

Le moteur consomme exclusivement :

* le total d'XP ;
* les règles de progression définies par le domaine.

---

# 4. Sorties

Le moteur produit un **Level Report** contenant notamment :

* niveau actuel ;
* XP totale ;
* progression vers le niveau suivant ;
* XP restante avant le prochain niveau ;
* version des règles métier ;
* horodatage.

Ce rapport est immuable.

---

# 5. Principes métier

## Progression continue

Chaque niveau représente une étape franchie de manière définitive.

---

## Déterminisme

Pour une même quantité d'XP, le niveau obtenu est toujours identique.

---

## Explicabilité

Chaque changement de niveau doit être justifiable par l'évolution de l'XP.

---

## Neutralité

Le niveau reflète uniquement la progression dans Project Rebuild.

Il ne constitue jamais un jugement de valeur.

---

# 6. Changement de niveau

Lorsqu'un seuil est franchi :

* le nouveau niveau est validé ;
* le rapport est mis à jour ;
* les événements métier sont publiés.

Le moteur ne déclenche aucune action utilisateur.

---

# 7. Interactions

Le résultat peut être consommé par :

* Badge Engine ;
* Achievement Engine ;
* Rebuild Engine ;
* Coach Engine ;
* Analytics Engine.

Le Level Engine dépend uniquement du XP Engine.

---

# 8. Contraintes

Le moteur garantit :

* calcul reproductible ;
* absence de régression de niveau (sauf règle métier explicite) ;
* historique cohérent ;
* indépendance technologique.

---

# 9. Événements publiés

Le moteur peut publier :

* LevelReached
* LevelUp
* LevelProgressUpdated

Ces événements décrivent exclusivement des faits métier.

---

# 10. Invariants

* un niveau dépend uniquement de l'XP ;
* aucun calcul aléatoire ;
* aucune dépendance à l'UI ;
* aucune dépendance à la base de données ;
* aucun accès direct aux autres Engines.

---

# 11. Dépendances

Le moteur dépend uniquement :

* des Entités du domaine ;
* des Value Objects ;
* des Domain Services ;
* des Domain Events ;
* des résultats produits par le XP Engine.

---

# 12. Résumé

Le Level Engine transforme l'expérience accumulée en niveaux de progression durables. Il garantit un calcul déterministe, reproductible et indépendant de toute technologie, servant de référence à l'ensemble des mécanismes de progression.
