# Frontend API Client Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'architecture du client API utilisé par le Frontend de Project Rebuild.

Le client API constitue la couche de communication entre l'interface utilisateur et le Backend.

Son objectif est de fournir une communication fiable, structurée et indépendante des composants UI.

---

# 2. Principes

Le client API respecte les principes suivants :

* séparation communication / interface ;
* contrats clairement définis ;
* gestion centralisée des erreurs ;
* faible couplage ;
* testabilité.

---

# 3. Responsabilités

Le client API est responsable de :

* envoyer les requêtes au Backend ;
* recevoir les réponses ;
* gérer les erreurs techniques ;
* transformer les formats nécessaires ;
* appliquer les règles de communication.

---

# 4. Non-responsabilités

Le client API ne doit jamais :

* contenir de logique métier ;
* calculer une progression ;
* interpréter les décisions des Engines ;
* modifier directement l'état métier.

---

# 5. Organisation

Le client API est organisé autour des capacités Backend.

Exemples conceptuels :

```text
API Client
│
├── User API
│
├── Mission API
│
├── Progression API
│
├── Avatar API
│
├── Coach API
│
└── Analytics API
```

---

# 6. Contrats

Les échanges reposent sur des contrats définis côté Backend.

Le Frontend dépend uniquement de :

* structures de requêtes ;
* structures de réponses ;
* codes d'erreurs ;
* règles de communication.

---

# 7. Authentification

Le client API doit gérer :

* transmission des informations d'authentification ;
* renouvellement de session ;
* expiration ;
* erreurs d'accès.

Les décisions d'autorisation restent côté Backend.

---

# 8. Gestion des erreurs

Les erreurs reçues doivent être transformées en états exploitables par l'interface.

Exemples :

* erreur réseau ;
* erreur serveur ;
* erreur d'autorisation ;
* erreur métier.

---

# 9. Performance

Le client API doit permettre :

* limitation des requêtes inutiles ;
* gestion efficace du cache ;
* récupération contrôlée des données.

---

# 10. Tests

Le client API doit pouvoir être testé indépendamment :

* tests de communication ;
* tests des transformations ;
* tests des erreurs.

---

# 11. Invariants

Le client API respecte toujours :

* aucune logique métier ;
* Backend comme source de vérité ;
* communication centralisée ;
* contrats stables ;
* indépendance des composants UI.

---

# 12. Résumé

Le client API de Project Rebuild fournit une couche de communication robuste entre le Frontend et le Backend. Il protège l'interface des détails techniques tout en maintenant une séparation stricte avec le Domaine.
