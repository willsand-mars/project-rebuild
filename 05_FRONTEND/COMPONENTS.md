# Component Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit l'architecture des composants Frontend de Project Rebuild.

Les composants constituent les briques visuelles et interactives utilisées pour construire l'expérience utilisateur.

---

# 2. Principes

Chaque composant doit respecter :

* responsabilité unique ;
* réutilisabilité ;
* isolation ;
* testabilité ;
* cohérence avec le Design System.

---

# 3. Catégories de composants

Les composants sont organisés selon plusieurs niveaux.

---

# 3.1 Atomic Components

Composants fondamentaux.

Exemples :

* Button ;
* Icon ;
* Badge ;
* ProgressBar ;
* AvatarFrame.

Ils ne connaissent aucun contexte métier.

---

# 3.2 Interface Components

Composants combinant plusieurs éléments visuels.

Exemples :

* Card ;
* Modal ;
* Panel ;
* NavigationBar.

Ils construisent l'interface.

---

# 3.3 Feature Components

Composants liés à une capacité fonctionnelle.

Exemples :

* MissionDisplay ;
* HabitTracker ;
* XPOverview ;
* CoachConversation.

Ils affichent des données métier reçues du Backend.

---

# 3.4 Layout Components

Responsables de la structure des écrans.

Exemples :

* DashboardLayout ;
* MobileLayout ;
* DesktopLayout.

---

# 4. Responsabilités

Un composant peut :

* afficher ;
* recevoir des données ;
* gérer des interactions locales.

Un composant ne peut jamais :

* calculer une règle métier ;
* décider une récompense ;
* modifier directement le Domaine.

---

# 5. Communication

Les composants communiquent via :

* propriétés ;
* événements UI ;
* gestion d'état locale ou globale.

Les échanges métier passent toujours par les couches applicatives.

---

# 6. États

Chaque composant définit ses états :

* initial ;
* chargement ;
* succès ;
* erreur ;
* vide.

Ces états doivent être cohérents dans toute l'application.

---

# 7. Performance

Les composants doivent être conçus pour :

* limiter les rendus inutiles ;
* favoriser la réutilisation ;
* permettre une évolution progressive.

---

# 8. Tests

Chaque composant important doit pouvoir être testé indépendamment.

Les tests vérifient :

* affichage ;
* interactions ;
* comportements attendus.

---

# 9. Invariants

L'architecture composants garantit :

* aucune logique métier dans l'UI ;
* composants indépendants ;
* cohérence visuelle ;
* évolutivité.

---

# 10. Résumé

L'architecture des composants Frontend fournit une base solide pour construire l'interface Project Rebuild. Elle permet de créer une expérience riche et immersive tout en conservant une séparation stricte entre présentation et logique métier.
