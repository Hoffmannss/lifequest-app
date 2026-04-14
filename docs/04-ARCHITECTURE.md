# 04 — System Architecture

**Status:** Pre-construction draft
**Last Updated:** April 2026

---

## High-Level Architecture

```
┌───────────────────────────────────────────────────┐
│           LIFEQUEST MOBILE APP (Flutter)           │
├───────────────────────────────────────────────────┤
│  UI Layer         │  State Layer    │  Data Layer   │
│  (Widgets/Screens)│  (Riverpod)     │  (Repos/APIs)  │
└───────────────────────────────────────────────────┘
         │                    │
    ┌────┴─────┐           ┌───┴───────┐
    │  Firebase  │           │ OpenAI API  │
    │  (Backend) │           │ (AI Mentor) │
    ├───────────┤           └───────────┘
    │ Firestore  │
    │ Auth       │
    │ Functions  │
    │ Storage    │
    │ FCM        │
    └───────────┘
```

---

## App Layer Structure (Clean Architecture)

```
lib/
├── main.dart
├── app/
│   ├── app.dart              # App root widget
│   ├── router.dart           # GoRouter configuration
│   └── theme.dart            # App theme & design tokens
├── features/
│   ├── auth/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   ├── onboarding/
│   ├── dashboard/
│   ├── quests/
│   ├── skills/
│   ├── ai_mentor/
│   ├── achievements/
│   ├── profile/
│   └── settings/
├── core/
│   ├── constants/
│   ├── utils/
│   ├── extensions/
│   ├── errors/
│   └── services/
└── shared/
    ├── widgets/
    ├── animations/
    └── models/
```

---

## Core Data Models

### User
```dart
class User {
  final String id;
  final String name;
  final String email;
  final int globalLevel;
  final int totalXP;
  final int currentStreak;
  final int longestStreak;
  final DateTime createdAt;
  final DateTime lastActiveAt;
  final UserProfile aiProfile; // AI mentor context
  final List<String> activeSkillIds;
}
```

### Skill
```dart
class Skill {
  final String id;
  final String userId;
  final String name;
  final String emoji;
  final SkillCategory category;
  final int level;          // 1-100
  final int currentXP;
  final int xpToNextLevel;
  final int streak;
  final DateTime startedAt;
  final List<Quest> todayQuests;
  final SkillHistory history;
}
```

### Quest
```dart
class Quest {
  final String id;
  final String skillId;
  final String title;
  final String description;
  final String whyItMatters;
  final int estimatedMinutes;
  final int xpReward;
  final QuestDifficulty difficulty; // easy, medium, hard
  final bool isCompleted;
  final DateTime? completedAt;
  final DateTime scheduledFor;
  final QuestType type; // practice, learn, create, review
}
```

### AIProfile (User Context for AI)
```dart
class AIProfile {
  final String userId;
  final String goals;           // "I want to become a DJ"
  final String schedule;        // "Free in evenings, 1h max/day"
  final String learningStyle;   // "Hands-on, visual"
  final String currentLevels;   // "Piano: beginner, DJ: never tried"
  final List<String> completedMilestones;
  final String recentFeedback;  // What the user said about tasks
  final DateTime lastUpdated;
}
```

---

## AI Quest Generation Flow

```
User Action: "Add Cooking to my skills"
        ↓
App sends to Firebase Cloud Function:
  - User AIProfile
  - New skill: "Cooking"
  - Current active skills + levels
  - Today's date + available time
        ↓
Cloud Function builds prompt:
  System: "You are a personal life coach..."
  User context: [AIProfile data]
  Request: "Generate 3 quests for day 1 of Cooking"
        ↓
OpenAI GPT-4o responds with JSON:
  [
    {title, description, why, minutes, xp, difficulty},
    ...
  ]
        ↓
Cloud Function validates + stores in Firestore
        ↓
App receives quests, displays with animation
        ↓
User sees: "Your Cooking journey begins!"
```

---

## Daily Quest Regeneration

```
Scheduled Cloud Function (runs at 00:00 user timezone)
        ↓
Fetch all active users with skills
        ↓
For each user:
  - Review yesterday's completed quests
  - Check streak status
  - Determine difficulty progression
  - Generate new quests via AI
        ↓
Store new quests in Firestore
        ↓
Send push notification: "Your quests for today are ready!"
```

---

## Security Architecture

| Layer | Mechanism |
|---|---|
| **Authentication** | Firebase Auth (Apple Sign-In required for iOS) |
| **Data Access** | Firestore Security Rules — users can only read/write own data |
| **API Security** | OpenAI API key stored in Cloud Functions env vars (never in app) |
| **Transport** | HTTPS/TLS 1.3 for all connections |
| **Data Encryption** | Firebase encrypts data at rest by default |
| **Payments** | RevenueCat handles all payment data — we never touch card data |

---

## Firestore Data Structure

```
firestore/
├── users/{userId}/
│   ├── profile
│   ├── aiProfile
│   ├── skills/{skillId}/
│   │   ├── info
│   │   └── quests/{questId}
│   ├── achievements/{achievementId}
│   └── history/{date}
└── achievements/ (global definitions)
    └── {achievementId}
```

---

## Offline Strategy (v1.0)

- **Firestore offline persistence** enabled — last fetched quests available offline
- User can mark quests complete offline; sync when back online
- AI Mentor requires internet (cannot generate quests offline)
- Full offline mode planned for v2.0 with local AI model

---

*Architecture authored by: Hoffmannss*
*Subject to revision during development*
