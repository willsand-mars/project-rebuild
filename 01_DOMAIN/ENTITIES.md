# ENTITIES

Version : 0.1

---

# Définition

Une entité possède :

- une identité unique (UUID)
- un cycle de vie
- un historique
- un état

Toutes les entités héritent de BaseEntity.

---

# BaseEntity

id

createdAt

updatedAt

deletedAt (nullable)

version

status

---

# User

Représente un compte.

Responsabilités

- connexion
- sécurité
- abonnement

Possède :

- plusieurs Profiles

Ne possède jamais directement :

- repas
- entraînements
- objectifs

---

# Profile

Représente une identité sportive.

Exemples :

- Fighter
- Weight Loss
- Marathon
- Bodybuilding

Contient :

Informations physiques

Préférences

Objectifs

Progression

Un User peut posséder plusieurs Profiles.

---

# Assessment

Photographie d'un profil à une date donnée.

Contient :

- âge
- taille
- poids
- IMC
- Rebuild Index
- masse grasse
- masse musculaire
- niveau sportif
- calories maintenance

Ne change jamais.

Un nouvel Assessment est créé à chaque réévaluation.

---

# Goal

Objectif principal.

Exemples :

Prendre 8 kg.

Faire 15 tractions.

Perdre 10 kg.

Un Goal possède :

- une priorité
- une échéance
- un état
- plusieurs Missions

---

# Mission

Action concrète.

Toujours :

mesurable

réalisable

temporelle

Exemples :

Boire 3 litres.

Faire 40 pompes.

Dormir 8 heures.

Marcher 8000 pas.

---

# Program

Ensemble structuré.

Peut contenir :

Workout Plans

Nutrition Plans

Recovery Plans

Mission Packs

---

# Workout

Séance complète.

Exemple :

Upper Body A

Contient :

plusieurs Exercises

---

# Exercise

Mouvement unique.

Exemple :

Squat

Pompes

Tractions

Développé couché

---

# WorkoutLog

Historique d'une séance.

Contient :

date

temps

charges

volume

ressenti

---

# Food

Aliment.

Exemple :

Riz

Poulet

Banane

Possède :

Calories

Macros

Micronutriments

---

# Recipe

Recette.

Contient plusieurs Foods.

---

# Meal

Repas consommé.

Possède :

heure

aliments

calories

macros

---

# Supplement

Complément alimentaire.

Exemple :

Créatine

Magnésium

Vitamine D

---

# ProgressEntry

État du profil à une date.

Poids

Mensurations

Photos

Force

Cardio

Notes

---

# Achievement

Condition de déblocage.

Exemple :

10 séances terminées.

---

# Badge

Récompense graphique.

Débloquée uniquement par un Achievement.

---

# XPTransaction

Historique des gains d'XP.

Jamais modifié.

Jamais supprimé.

---

# Level

Niveau actuel.

Calculé automatiquement.

---

# Notification

Message envoyé.

Peut être :

Push

Email

SMS

In-App

---

# CoachMessage

Conseil généré.

Possède :

source

raison

niveau de confiance

date

---

# Habit

Habitude quotidienne.

Exemples :

Dormir 8h

Boire 3L

Méditation

Lecture

---

# Streak

Compteur de régularité.

Toujours calculé.

Jamais saisi.

---

# JournalEntry

Entrée libre.

Texte

Photo

Humeur

Commentaires
