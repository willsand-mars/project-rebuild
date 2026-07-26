# Artificial Intelligence Architecture

**Version :** 1.0
**Statut :** Validé

---

# 1. Objectif

Ce document définit le rôle de l'Intelligence Artificielle dans Project Rebuild.

L'IA constitue une couche d'accompagnement intelligente permettant d'interpréter les données produites par le système afin de fournir une expérience personnalisée.

Elle n'est pas le centre du produit.

Le cœur du système reste :

```text
Domain
    ↓
Engines
    ↓
Rules
    ↓
Data
```

L'IA intervient uniquement après ces éléments.

---

# 2. Philosophie

Le Coach IA de Project Rebuild n'est pas :

* un médecin ;
* un entraîneur humain ;
* un décideur ;
* un générateur de règles.

Il est :

* un interprète ;
* un accompagnateur ;
* un facilitateur ;
* un guide personnalisé.

---

# 3. Principe fondamental

L'IA ne crée jamais la vérité.

Elle interprète uniquement des informations validées par le système.

Flux obligatoire :

```text
Utilisateur
      ↓
Données
      ↓
Domain
      ↓
Engines
      ↓
Résultats validés
      ↓
IA
      ↓
Explication personnalisée
      ↓
Utilisateur
```

---

# 4. Responsabilités

L'IA est responsable de :

* expliquer les résultats ;
* contextualiser la progression ;
* formuler des encouragements ;
* adapter la communication ;
* aider l'utilisateur à comprendre son parcours.

---

# 5. Non-responsabilités

L'IA ne doit jamais :

* calculer le Rebuild Index ;
* attribuer de l'XP ;
* créer une Mission ;
* modifier une règle métier ;
* remplacer un Engine ;
* prendre une décision critique seule.

---

# 6. Position dans l'architecture

```text
Vision
 ↓
Domain
 ↓
Engines
 ↓
Backend
 ↓
AI Layer
 ↓
Frontend
 ↓
Utilisateur
```

L'IA est une couche supérieure.

Elle dépend du système.

Le système ne dépend pas de l'IA.

---

# 7. Objectif utilisateur

L'utilisateur doit percevoir l'IA comme :

* un coach personnel ;
* une présence motivante ;
* un conseiller intelligent.

Mais jamais comme :

* un juge ;
* une autorité absolue ;
* une source magique de vérité.

---

# 8. Personnalisation

La personnalisation peut utiliser :

* historique de progression ;
* préférences utilisateur ;
* habitudes ;
* objectifs ;
* contexte fourni par les Engines.

Elle respecte toujours :

* confidentialité ;
* sécurité ;
* consentement utilisateur.

---

# 9. Fiabilité

Toute recommandation générée doit être :

* basée sur des données existantes ;
* explicable ;
* cohérente avec les règles du système.

---

# 10. Évolution

L'architecture doit permettre l'évolution future :

* nouveaux modèles IA ;
* nouvelles capacités ;
* amélioration des interactions.

Sans modifier :

* le Domaine ;
* les Engines ;
* les règles métier.

---

# 11. Invariants

L'architecture IA garantit :

* l'IA assiste mais ne décide pas ;
* les Engines restent propriétaires des calculs ;
* aucune hallucination métier ;
* séparation IA / Domaine ;
* contrôle permanent des données utilisées.

---

# 12. Résumé

L'Intelligence Artificielle de Project Rebuild est une couche d'accompagnement au-dessus du système métier.

Elle transforme des données objectives en compréhension humaine.

Elle aide l'utilisateur à progresser sans jamais remplacer la logique fondamentale du produit.
