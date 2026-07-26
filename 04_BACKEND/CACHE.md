# Cache Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de cache de Project Rebuild.

Le cache permet d'améliorer les performances du système en conservant temporairement des données fréquemment consultées ou coûteuses à reconstruire.

Le cache constitue une optimisation technique.

Il ne représente jamais une source de vérité métier.

---

# 2. Principes

Le système de cache respecte les principes suivants :

* amélioration des performances ;
* absence de dépendance métier ;
* cohérence contrôlée ;
* invalidation maîtrisée ;
* transparence pour le Domaine.

---

# 3. Responsabilités

Le cache est responsable de :

* stocker temporairement des données ;
* réduire les accès coûteux ;
* accélérer certaines lectures ;
* gérer l'expiration des données.

Il n'est jamais responsable de :

* prendre une décision métier ;
* remplacer une persistance durable ;
* modifier l'état du Domaine.

---

# 4. Types de cache

## Cache applicatif

Utilisé pour :

* résultats de traitements ;
* configurations temporaires ;
* données fréquemment consultées.

---

## Cache de lecture

Utilisé pour :

* projections ;
* tableaux de bord ;
* données destinées au Frontend.

---

## Cache technique

Utilisé pour :

* optimisation réseau ;
* réduction de charge ;
* ressources externes.

---

# 5. Données éligibles

Une donnée peut être mise en cache si :

* elle est coûteuse à calculer ;
* elle est fréquemment consultée ;
* son invalidation est maîtrisée.

---

# 6. Données non éligibles

Les éléments suivants ne doivent jamais dépendre uniquement du cache :

* état du Domaine ;
* Domain Events ;
* historique utilisateur ;
* transactions importantes.

---

# 7. Invalidation

L'invalidation du cache doit être contrôlée.

Elle peut intervenir :

* après une modification métier ;
* après expiration ;
* lors d'une opération de maintenance.

---

# 8. Cohérence

Le cache accepte une éventuelle désynchronisation temporaire uniquement lorsque cela ne compromet pas les règles métier.

La source de vérité reste toujours le stockage principal.

---

# 9. Gestion des erreurs

Si le cache devient indisponible :

* le système doit pouvoir continuer selon les possibilités ;
* aucune donnée métier ne doit être perdue ;
* l'erreur doit être observable.

---

# 10. Sécurité

Le cache doit respecter :

* isolation des utilisateurs ;
* protection des données sensibles ;
* contrôle des accès.

---

# 11. Invariants

Le système respecte toujours les règles suivantes :

* le cache est optionnel ;
* le Domaine ne dépend jamais du cache ;
* aucune donnée critique n'existe uniquement en cache ;
* aucune logique métier dans le mécanisme de cache.

---

# 12. Résumé

La stratégie de cache de Project Rebuild améliore les performances tout en conservant une séparation stricte entre optimisation technique et logique métier. Le cache accélère le système sans jamais devenir une source de vérité.
