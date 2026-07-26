# Frontend Routing Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'organisation de la navigation dans le Frontend de Project Rebuild.

Le système de routing permet d'organiser les différents espaces de l'application tout en conservant une expérience utilisateur fluide et cohérente.

---

# 2. Principes

Le routing respecte :

* navigation claire ;
* séparation des espaces fonctionnels ;
* contrôle des accès ;
* URLs stables ;
* expérience immersive.

---

# 3. Responsabilités

Le système de routing est responsable de :

* afficher le bon écran ;
* gérer les transitions ;
* protéger les espaces nécessitant une authentification ;
* maintenir le contexte utilisateur.

Il n'est jamais responsable de :

* prendre des décisions métier ;
* calculer une progression ;
* gérer les règles du Domaine.

---

# 4. Organisation logique

La navigation est organisée autour des grands espaces utilisateur.

Exemples conceptuels :

```text id="8g1p9a"
/
│
├── onboarding
│
├── dashboard
│
├── missions
│
├── habits
│
├── progression
│
├── avatar
│
├── coach
│
└── profile
```

La structure finale dépendra des besoins validés du produit.

---

# 5. Navigation authentifiée

Les espaces personnels nécessitent :

* identité utilisateur valide ;
* session active ;
* autorisation appropriée.

---

# 6. Navigation publique

Les espaces publics permettent notamment :

* découverte ;
* présentation ;
* authentification.

---

# 7. Transitions

Les transitions doivent respecter l'identité Project Rebuild :

* fluidité ;
* animations maîtrisées ;
* continuité visuelle.

Elles ne doivent jamais ralentir l'accès à l'information.

---

# 8. Deep Linking

Le système doit permettre :

* accès direct à un espace ;
* partage contrôlé ;
* restauration de navigation.

---

# 9. Gestion des erreurs

Les situations suivantes doivent être gérées :

* route inexistante ;
* accès refusé ;
* session expirée ;
* ressource indisponible.

---

# 10. Invariants

Le routing respecte toujours :

* aucune logique métier ;
* aucune dépendance aux données internes ;
* contrôle des accès séparé ;
* navigation cohérente.

---

# 11. Résumé

L'architecture de navigation Frontend de Project Rebuild fournit une structure claire et immersive permettant à l'utilisateur d'explorer son parcours de transformation tout en conservant une séparation stricte avec le Domaine.
