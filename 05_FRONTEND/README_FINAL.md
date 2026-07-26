# Frontend Architecture Summary

**Version :** 1.0
**Statut :** Validé

---

# 1. Introduction

Le Frontend de Project Rebuild constitue la couche d'expérience utilisateur du système.

Son rôle est de transformer les capacités métier définies par le Domaine, les Engines et le Backend en une interface immersive, claire et motivante.

Le Frontend n'est pas propriétaire des règles métier.

Il représente le système.

---

# 2. Position architecturale

L'architecture globale respecte :

```text id="3k2v9h"
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

Chaque couche possède une responsabilité précise.

---

# 3. Responsabilité du Frontend

Le Frontend est responsable de :

* l'expérience utilisateur ;
* la présentation des informations ;
* les interactions ;
* l'immersion ;
* les animations ;
* la communication avec le Backend.

---

# 4. Séparation fondamentale

Le Frontend ne contient jamais :

* règles métier ;
* calcul du Rebuild Index ;
* calcul XP ;
* décisions du Coach IA ;
* logique de récompense ;
* logique d'évolution utilisateur.

Toutes les décisions proviennent du système métier.

---

# 5. Architecture Frontend

La structure générale repose sur :

```text id="o4f7x1"
UI Components
       ↓
Presentation Logic
       ↓
Frontend State
       ↓
API Client
       ↓
Backend
```

Chaque couche reste indépendante.

---

# 6. Design System

Le Design System garantit :

* identité visuelle constante ;
* composants réutilisables ;
* cohérence graphique.

L'identité Project Rebuild repose sur :

* rétro-futurisme années 80 ;
* néons ;
* violet ;
* rose ;
* cyan ;
* glassmorphism ;
* animations fluides.

---

# 7. Expérience utilisateur

L'application doit donner la sensation :

* d'un parcours ;
* d'une évolution ;
* d'une transformation.

L'utilisateur ne consulte pas simplement des données.

Il suit son aventure personnelle.

---

# 8. Composants

Les composants sont organisés selon plusieurs niveaux :

```text id="q2d6k9"
Atomic Components

        ↓

Interface Components

        ↓

Feature Components

        ↓

Layout Components
```

Chaque composant possède une responsabilité claire.

---

# 9. Gestion des états

Les états sont séparés :

## Server State

Données officielles provenant du Backend.

Exemples :

* progression ;
* missions ;
* XP ;
* badges ;
* profil.

---

## Client State

Données temporaires liées à l'interface.

Exemples :

* navigation ;
* animations ;
* affichages temporaires.

---

# 10. Communication Backend

Le Frontend communique uniquement via le Client API.

Il ne connaît jamais :

* la base de données ;
* les repositories ;
* les services internes ;
* les Engines.

---

# 11. Navigation

Le routing organise les espaces utilisateur :

* onboarding ;
* dashboard ;
* missions ;
* habitudes ;
* progression ;
* avatar ;
* coach ;
* profil.

La navigation reste indépendante du Domaine.

---

# 12. Animations

Les animations servent à :

* renforcer la progression ;
* donner du feedback ;
* augmenter l'immersion.

Elles ne modifient jamais l'état métier.

---

# 13. Gestion des erreurs

Les erreurs sont transformées en informations compréhensibles.

Le Frontend :

* affiche ;
* explique ;
* propose une récupération.

Il ne corrige jamais une décision métier.

---

# 14. Accessibilité

L'identité visuelle forte reste compatible avec :

* lisibilité ;
* contraste ;
* navigation claire ;
* adaptation utilisateur.

---

# 15. Responsive Design

L'expérience fonctionne sur :

* mobile ;
* tablette ;
* desktop.

L'approche privilégiée est :

```text id="v8n2px"
Mobile First
      ↓
Adaptation progressive
```

---

# 16. Principes immuables

Le Frontend respecte toujours :

* aucune logique métier ;
* Backend comme source de vérité ;
* composants réutilisables ;
* architecture modulaire ;
* séparation claire des responsabilités.

---

# 17. Structure finale du dossier

```text id="h7k3mp"
05_FRONTEND/

├── README.md
├── ARCHITECTURE.md
├── DESIGN_SYSTEM.md
├── COMPONENTS.md
├── STATE_MANAGEMENT.md
├── ROUTING.md
├── ANIMATIONS.md
├── THEME.md
├── API_CLIENT.md
├── ERROR_HANDLING.md
├── LOADING_STATES.md
├── ACCESSIBILITY.md
├── RESPONSIVE_DESIGN.md
└── README_FINAL.md
```

---

# 18. Conclusion

Le Frontend de Project Rebuild constitue la passerelle entre le moteur métier et l'utilisateur.

Son objectif n'est pas seulement d'afficher des informations.

Il transforme les décisions du système en une expérience de progression immersive.

L'utilisateur ne gère pas une application.

Il vit son évolution.

---

**Fin officielle du dossier `05_FRONTEND/`**
