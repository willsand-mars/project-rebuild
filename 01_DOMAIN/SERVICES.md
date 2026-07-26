# DOMAIN SERVICES

Version : 0.1

---

# Définition

Un Domain Service contient une logique métier qui ne peut pas appartenir naturellement à une seule entité.

Un Service :

- ne stocke pas de données
- est stateless
- orchestre plusieurs entités
- applique des règles métier

---

# Assessment Service

Responsabilités

- Évaluer un Profile
- Déclencher les moteurs de calcul
- Produire un Assessment

Entrées

- Profile
- Measurements

Sorties

- Assessment

---

# Goal Service

Responsabilités

- Créer un Goal
- Vérifier sa cohérence
- Gérer les changements d'état
- Clôturer un Goal

---

# Mission Service

Responsabilités

- Générer des Missions
- Attribuer des récompenses
- Vérifier leur réalisation
- Marquer une Mission comme terminée

---

# Nutrition Service

Responsabilités

- Générer un plan alimentaire
- Calculer les besoins énergétiques
- Construire les repas
- Adapter les calories

---

# Workout Service

Responsabilités

- Générer un programme
- Construire les séances
- Adapter la progression
- Calculer le volume

---

# Recovery Service

Responsabilités

- Évaluer la récupération
- Ajuster la charge
- Prévenir le surentraînement

---

# Progress Service

Responsabilités

- Enregistrer les progrès
- Comparer les historiques
- Détecter les plateaux

---

# Gamification Service

Responsabilités

- Attribuer l'XP
- Calculer les niveaux
- Débloquer les Badges
- Gérer les Streaks

---

# Coach Service

Responsabilités

- Générer les recommandations
- Expliquer les décisions
- Adapter les conseils

Le Coach ne modifie jamais directement les données.

---

# Notification Service

Responsabilités

- Construire les notifications
- Planifier les rappels
- Éviter les doublons

---

# Analytics Service

Responsabilités

- Produire des statistiques
- Alimenter les tableaux de bord
- Exporter les données

---

# Service Rules

Les Services :

- ne contiennent aucune logique d'interface
- ne dépendent pas de la base de données
- ne dépendent pas des API
- ne dépendent pas de l'IA
- utilisent uniquement le domaine métier
