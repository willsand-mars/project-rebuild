# Notification Engine

**Version :** 1.0
**Statut :** Validé
**Couche :** Business Engine

---

# 1. Objectif

Le **Notification Engine** est responsable de la production des événements de notification destinés aux différentes couches de diffusion.

Sa mission consiste à déterminer **quand** une notification doit être émise et **pour quelle raison métier**, sans jamais décider de sa présentation ou de son canal de diffusion.

Le moteur ne contient aucun contenu textuel.

---

# 2. Responsabilités

Le Notification Engine est responsable de :

* détecter les événements nécessitant une notification ;
* appliquer les règles métier de déclenchement ;
* éviter les notifications redondantes ;
* prioriser les notifications ;
* publier les événements de notification.

Il n'est jamais responsable de :

* envoyer des notifications ;
* générer le contenu des messages ;
* choisir une langue ;
* gérer les appareils utilisateurs ;
* communiquer avec Apple Push Notification Service (APNs), Firebase Cloud Messaging (FCM), le courrier électronique ou tout autre fournisseur.

---

# 3. Entrées

Le moteur consomme les événements publiés par les autres Engines.

Exemples :

* LevelUp
* BadgeUnlocked
* AchievementUnlocked
* MissionCompleted
* StreakBroken
* RebuildTrendChanged

---

# 4. Décision métier

Pour chaque événement reçu, le moteur détermine :

* si une notification est pertinente ;
* son niveau de priorité ;
* sa catégorie ;
* son délai éventuel ;
* si elle peut être regroupée avec d'autres notifications.

La diffusion reste entièrement extérieure au moteur.

---

# 5. Priorités

Chaque notification possède un niveau de priorité métier.

Exemples :

* Information
* Progression
* Important
* Critique

Ces niveaux n'impliquent aucun canal technique.

---

# 6. Sorties

Le moteur produit un **Notification Decision Report** contenant notamment :

* événement source ;
* catégorie ;
* priorité ;
* justification métier ;
* horodatage ;
* version des règles.

Le rapport est immuable.

---

# 7. Principes métier

## Pertinence

Une notification doit toujours avoir une valeur pour l'utilisateur.

---

## Non-intrusion

Le moteur limite les notifications inutiles ou répétitives.

---

## Explicabilité

Chaque décision de notification doit pouvoir être justifiée.

---

## Découplage

Le moteur ne connaît jamais le système chargé de diffuser les notifications.

---

# 8. Interactions

Le Notification Engine reçoit des événements de l'ensemble des Business Engines.

Il publie ensuite des événements consommés par la couche Infrastructure.

---

# 9. Contraintes

Le moteur garantit :

* aucune notification dupliquée ;
* traitement idempotent ;
* indépendance technologique ;
* règles entièrement déterministes.

---

# 10. Événements publiés

Le moteur peut publier :

* NotificationRequested
* NotificationCancelled
* NotificationGrouped
* NotificationDeferred

Ces événements représentent exclusivement des décisions métier.

---

# 11. Invariants

Le Notification Engine respecte les règles suivantes :

* aucune logique d'affichage ;
* aucun contenu textuel ;
* aucun accès aux services de notification ;
* aucune dépendance à l'interface utilisateur ;
* uniquement des décisions métier.

---

# 12. Dépendances

Le moteur dépend uniquement :

* des Domain Events ;
* des Entités ;
* des Value Objects ;
* des Domain Services.

---

# 13. Résumé

Le Notification Engine transforme les événements métier en décisions de notification. Il garantit que seules les informations pertinentes sont publiées, tout en restant totalement indépendant des technologies de diffusion et de la présentation des messages.
