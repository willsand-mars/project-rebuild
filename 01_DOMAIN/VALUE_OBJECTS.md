# VALUE OBJECTS

Version : 0.1

---

# Définition

Un Value Object :

- ne possède pas d'identité (UUID)
- est immutable (jamais modifié)
- est remplacé lorsqu'il change
- contient ses propres règles de validation

Deux Value Objects ayant exactement les mêmes valeurs sont identiques.

---

# Age

Représente l'âge d'un utilisateur.

Règles

minimum : 13 ans

maximum : 120 ans

Unité

Années

---

# Height

Représente une taille.

Unité interne

centimètres

Affichage

cm

ft/in

Validation

100 cm

↓

250 cm

---

# Weight

Représente un poids.

Unité interne

kilogrammes

Affichage

kg

lb

Validation

20 kg

↓

350 kg

---

# BodyFat

Pourcentage de masse grasse.

Unité

%

Validation

2%

↓

70%

---

# MuscleMass

Masse musculaire.

Unité

kg

Validation

positive uniquement

---

# Calories

Énergie.

Unité

kcal

Validation

0

↓

15000 kcal

---

# Macronutrients

Objet composé.

Contient

Protein

Carbohydrates

Fat

Fiber

Sugar

Chaque valeur est exprimée en grammes.

---

# Protein

Grammes.

Toujours positif.

---

# Carbohydrates

Grammes.

Toujours positif.

---

# Fat

Grammes.

Toujours positif.

---

# Water

Hydratation.

Unité

millilitres

Affichage

L

mL

---

# Distance

Unité interne

mètres

Affichage

m

km

mile

---

# Duration

Temps.

Unité interne

secondes

Affichage

minutes

heures

---

# HeartRate

Fréquence cardiaque.

Unité

BPM

Validation

20

↓

250

---

# BloodPressure

Objet composé.

Systolique

Diastolique

---

# Sleep

Objet composé.

Contient

Durée

Qualité

Heure de coucher

Heure de réveil

Interruptions

---

# BMI

Objet calculé.

Jamais enregistré.

Toujours recalculé.

---

# Rebuild Index

Objet calculé.

Produit par Assessment Engine.

Jamais modifié manuellement.

---

# XP

Points d'expérience.

Toujours positifs.

Jamais négatifs.

---

# Level

Calculé.

Jamais saisi.

---

# Percentage

Valeur générique.

0

↓

100

---

# Score

Valeur générique.

0

↓

1000

---

# Money

Toujours stocké dans la devise de référence.

Affichage localisé.

---

# DateRange

Objet composé.

Date début

Date fin

Validation

Début < Fin

---

# GPSLocation

Latitude

Longitude

Altitude

Optionnel.

---

# Mood

Enum.

Très mauvais

Mauvais

Neutre

Bon

Excellent

---

# Difficulty

Enum.

Very Easy

Easy

Medium

Hard

Extreme

---

# Priority

Enum.

Low

Medium

High

Critical

---

# Language

ISO-639

fr

en

vi

...

---

# UnitSystem

Metric

Imperial

---

# Theme

Dark

Light

System

---

# Gender

Ne pas coder en dur.

Utiliser une liste configurable.

---

# ActivityLevel

Sedentary

Light

Moderate

Active

Athlete

---

# GoalType

Muscle Gain

Fat Loss

Performance

Maintenance

Wellness

Custom

---

# Validation

Tous les Value Objects réalisent eux-mêmes leur validation.

Le reste du logiciel ne valide jamais directement ces données.
