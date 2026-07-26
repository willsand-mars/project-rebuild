# Frontend State Management

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit la stratégie de gestion des états dans le Frontend de Project Rebuild.

La gestion d'état permet de maintenir une interface cohérente, réactive et prévisible tout en séparant clairement les données métier des données propres à l'expérience utilisateur.

---

# 2. Principes

La gestion d'état respecte les principes suivants :

* source de vérité clairement définie ;
* séparation état serveur / état client ;
* absence de logique métier dans l'état Frontend ;
* prévisibilité des changements ;
* testabilité.

---

# 3. Types d'état

Project Rebuild distingue plusieurs catégories d'états.

---

# 3.1 Server State

Le Server State représente les données provenant du Backend.

Exemples :

* profil utilisateur ;
* niveau actuel ;
* XP disponible ;
* missions actives ;
* habitudes ;
* badges ;
* progression.

Ces données appartiennent au Domaine.

Le Frontend ne les modifie jamais directement.

---

# 3.2 Client State

Le Client State représente les informations nécessaires uniquement à l'interface.

Exemples :

* écran actif ;
* menu ouvert ;
* animation en cours ;
* préférences d'affichage temporaires.

---

# 3.3 UI State

L'UI State concerne l'état immédiat des composants.

Exemples :

* bouton sélectionné ;
* formulaire en édition ;
* affichage d'une fenêtre.

---

# 4. Source de vérité

La règle fondamentale est :

```text id="d5lq2k"
Backend
   ↓
Source métier officielle

Frontend
   ↓
Représentation temporaire
```

Le Frontend ne devient jamais propriétaire d'une donnée métier.

---

# 5. Synchronisation

La synchronisation avec le Backend doit garantir :

* données actualisées ;
* gestion des erreurs ;
* cohérence d'affichage ;
* récupération après interruption.

---

# 6. Mutations

Toute modification métier suit obligatoirement :

```text id="8j3t9w"
Action utilisateur
        ↓
Command API
        ↓
Backend
        ↓
Validation Domaine
        ↓
Nouvel état
        ↓
Mise à jour Frontend
```

---

# 7. Cache Frontend

Un cache côté client peut être utilisé pour :

* améliorer la vitesse ;
* limiter les requêtes ;
* améliorer l'expérience.

Cependant :

* il ne remplace jamais le Backend ;
* il ne contient aucune décision métier ;
* il doit pouvoir être invalidé.

---

# 8. Gestion des erreurs

Chaque état doit pouvoir représenter :

* chargement ;
* succès ;
* absence de données ;
* erreur ;
* récupération.

L'utilisateur doit toujours comprendre la situation.

---

# 9. Performance

La gestion d'état doit permettre :

* limiter les mises à jour inutiles ;
* éviter les duplications ;
* optimiser les écrans complexes.

---

# 10. Invariants

La gestion d'état respecte toujours :

* aucune règle métier dans le Frontend ;
* Backend comme source de vérité ;
* séparation données métier / interface ;
* états explicites ;
* synchronisation contrôlée.

---

# 11. Résumé

La gestion d'état Frontend de Project Rebuild garantit une interface réactive et fiable tout en maintenant une séparation stricte entre les données métier appartenant au système et les états temporaires nécessaires à l'expérience utilisateur.
