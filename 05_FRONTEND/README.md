# Frontend Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit le rôle et les principes fondamentaux de l'architecture Frontend de Project Rebuild.

Le Frontend représente l'expérience utilisateur.

Il transforme les capacités du système métier en une expérience immersive, interactive et cohérente avec l'identité du produit.

---

# 2. Position dans l'architecture

```text
Vision
    ↓
Domain
    ↓
Engines
    ↓
Database
    ↓
Backend
    ↓
Frontend
    ↓
Utilisateur
```

Le Frontend consomme le système.

Il ne définit jamais les règles métier.

---

# 3. Responsabilités

Le Frontend est responsable de :

* afficher les informations métier ;
* gérer les interactions utilisateur ;
* présenter les états du système ;
* orchestrer l'expérience utilisateur ;
* appliquer les principes UX/UI ;
* communiquer avec le Backend.

---

# 4. Non-responsabilités

Le Frontend ne doit jamais :

* calculer le Rebuild Index ;
* déterminer l'XP gagnée ;
* décider d'une récompense ;
* modifier une règle métier ;
* remplacer un Business Engine.

Toute décision appartient au Domaine ou aux Engines.

---

# 5. Philosophie utilisateur

Project Rebuild n'est pas présenté comme une application classique.

L'utilisateur doit ressentir :

* une progression ;
* une aventure ;
* une transformation ;
* une évolution personnelle.

L'interface transforme les actions quotidiennes en expérience motivante.

---

# 6. Identité visuelle

Le Frontend respecte l'identité Project Rebuild :

* ambiance rétro-futuriste années 80 ;
* néons ;
* violet ;
* rose ;
* cyan ;
* glassmorphism ;
* animations fluides ;
* univers Miami futuriste original.

---

# 7. Principes UX

L'expérience utilisateur suit les règles :

* motivation plutôt que culpabilité ;
* progression plutôt que perfection ;
* encouragement plutôt que jugement ;
* clarté plutôt que surcharge.

---

# 8. Architecture

Le Frontend doit rester :

* modulaire ;
* composable ;
* testable ;
* scalable ;
* indépendant du Backend.

---

# 9. Organisation

Le Frontend sera structuré autour de :

* composants UI ;
* domaines fonctionnels ;
* gestion d'état ;
* services API ;
* animations ;
* design system.

---

# 10. Résumé

Le Frontend de Project Rebuild constitue la couche émotionnelle et interactive du produit. Il transforme les capacités métier définies par le Domaine en une expérience immersive, sans jamais contenir de logique métier.
