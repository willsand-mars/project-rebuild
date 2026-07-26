# API Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit les principes d'architecture des API de Project Rebuild.

Les API constituent le point d'entrée officiel des clients (Frontend, IA, services externes) vers les cas d'usage du système.

Les API exposent les capacités de l'application.

Elles ne contiennent aucune logique métier.

---

# 2. Responsabilités

Les API sont responsables de :

* recevoir les requêtes ;
* valider leur structure ;
* authentifier les appels ;
* transmettre les commandes et requêtes à la couche Application ;
* retourner les réponses.

Elles ne sont jamais responsables de :

* prendre des décisions métier ;
* effectuer des calculs métier ;
* accéder directement à la base de données.

---

# 3. Principes

Toutes les API respectent les principes suivants :

* stateless ;
* déterministes ;
* documentées ;
* versionnées ;
* sécurisées ;
* indépendantes de l'interface cliente.

---

# 4. Contrats

Chaque endpoint définit explicitement :

* son objectif ;
* ses paramètres ;
* son format de réponse ;
* ses erreurs possibles.

Les contrats sont considérés comme publics.

---

# 5. Versionnement

Toute évolution incompatible entraîne une nouvelle version d'API.

Les anciennes versions suivent une politique de dépréciation documentée.

---

# 6. Erreurs

Les API retournent des erreurs standardisées.

Chaque erreur comporte notamment :

* un code ;
* un message ;
* un identifiant de corrélation ;
* des informations exploitables par le client.

---

# 7. Sécurité

Toutes les API appliquent :

* authentification ;
* autorisation ;
* validation des entrées ;
* journalisation.

---

# 8. Observabilité

Chaque appel doit pouvoir être :

* tracé ;
* journalisé ;
* corrélé à une requête métier.

---

# 9. Invariants

Les API respectent toujours les règles suivantes :

* aucune logique métier ;
* aucun accès direct au stockage ;
* aucune dépendance au Frontend ;
* contrats versionnés ;
* réponses déterministes.

---

# 10. Résumé

Les API de Project Rebuild exposent les cas d'usage de manière sécurisée, stable et versionnée. Elles assurent le découplage entre les clients et le cœur du système tout en laissant les décisions au Domaine.
