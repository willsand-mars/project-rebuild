# Background Jobs Strategy

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie des traitements exécutés en arrière-plan dans Project Rebuild.

Les Background Jobs permettent d'exécuter des opérations qui ne nécessitent pas une réponse immédiate à l'utilisateur.

Ils garantissent la fluidité de l'expérience utilisateur tout en permettant l'exécution de traitements longs ou différés.

---

# 2. Principes

Les Background Jobs respectent les principes suivants :

* exécution asynchrone ;
* découplage avec les requêtes utilisateur ;
* résilience ;
* traçabilité ;
* idempotence.

---

# 3. Responsabilités

Les Background Jobs peuvent être responsables de :

* traitements différés ;
* génération de projections ;
* synchronisations ;
* calculs non bloquants ;
* maintenance technique.

Ils ne sont jamais responsables de :

* remplacer un cas d'usage métier ;
* contenir des règles métier ;
* modifier directement le Domaine sans passer par les mécanismes prévus.

---

# 4. Types de traitements

Les traitements en arrière-plan peuvent concerner :

## Projection Jobs

Responsables de :

* mettre à jour les modèles de lecture ;
* reconstruire des projections ;
* traiter les Domain Events.

---

## Maintenance Jobs

Responsables de :

* nettoyage technique ;
* optimisation ;
* vérifications système.

---

## Integration Jobs

Responsables de :

* communication avec des services externes ;
* synchronisation de données.

---

# 5. Exécution

Un Background Job suit généralement ce cycle :

```text id="a3x1cp"
Création du Job
        ↓
Mise en file d'attente
        ↓
Exécution
        ↓
Validation du résultat
        ↓
Traçabilité
        ↓
Terminaison
```

---

# 6. Idempotence

Chaque traitement doit être conçu pour pouvoir être rejoué sans provoquer d'état incohérent.

Cette contrainte est essentielle pour garantir la résilience du système.

---

# 7. Gestion des erreurs

En cas d'échec :

* l'erreur est enregistrée ;
* le contexte est conservé ;
* une nouvelle tentative peut être déclenchée si approprié ;
* les erreurs métier ne sont jamais masquées.

---

# 8. Priorités

Les Jobs peuvent posséder différents niveaux de priorité selon leur importance.

Les traitements critiques ne doivent pas être bloqués par des tâches secondaires.

---

# 9. Observabilité

Chaque Job doit permettre de connaître :

* son état ;
* sa durée ;
* son résultat ;
* ses erreurs ;
* son historique d'exécution.

---

# 10. Sécurité

Les Background Jobs doivent respecter :

* les mêmes règles d'autorisation que les traitements classiques ;
* la protection des données sensibles ;
* la traçabilité des opérations.

---

# 11. Invariants

Les Background Jobs respectent toujours :

* aucune logique métier dupliquée ;
* exécution contrôlée ;
* traçabilité complète ;
* possibilité de reprise ;
* indépendance des interfaces.

---

# 12. Résumé

Les Background Jobs permettent à Project Rebuild d'exécuter des traitements asynchrones de manière fiable et scalable. Ils améliorent les performances du système tout en conservant une séparation stricte entre orchestration technique et logique métier.
