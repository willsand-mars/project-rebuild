# DOMAIN EVENTS

Version : 0.1

---

# Définition

Un Domain Event représente un fait métier qui s'est produit.

Un événement est immuable.

Il décrit uniquement ce qui s'est passé.

Jamais ce qu'il faut faire.

---

# Identity

UserCreated

UserDeleted

UserLoggedIn

UserLoggedOut

PasswordChanged

---

# Profile

ProfileCreated

ProfileUpdated

ProfileArchived

---

# Assessment

AssessmentCreated

AssessmentUpdated

AssessmentCompleted

---

# Goals

GoalCreated

GoalStarted

GoalPaused

GoalCompleted

GoalCancelled

---

# Missions

MissionGenerated

MissionStarted

MissionCompleted

MissionFailed

MissionExpired

---

# Nutrition

MealLogged

RecipeCreated

NutritionPlanGenerated

CaloriesUpdated

HydrationGoalReached

---

# Training

WorkoutGenerated

WorkoutStarted

WorkoutCompleted

ExerciseCompleted

PersonalRecordBroken

---

# Recovery

SleepLogged

RecoveryImproved

FatigueDetected

OvertrainingDetected

---

# Progress

WeightUpdated

MeasurementAdded

ProgressPhotoAdded

MilestoneReached

---

# Gamification

XPEarned

LevelUp

BadgeUnlocked

AchievementUnlocked

StreakStarted

StreakBroken

RewardGranted

---

# Coach

RecommendationGenerated

WarningGenerated

MotivationGenerated

---

# Notifications

NotificationScheduled

NotificationSent

NotificationRead

---

# Analytics

DashboardUpdated

StatisticsGenerated

---

# Event Rules

Les événements sont :

- immuables
- horodatés
- historisés
- identifiés par UUID

Ils ne modifient jamais directement les données.

Ils permettent aux autres domaines de réagir.

---

# Exemple

WorkoutCompleted

↓

XPEarned

↓

LevelUp

↓

BadgeUnlocked

↓

NotificationSent

Chaque étape est déclenchée par un événement indépendant.
