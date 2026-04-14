# 03 — Tech Stack Decision

**Decision Date:** April 2026
**Status:** Decided — Flutter

---

## Decision Summary

**Chosen Framework: Flutter (Dart)**

After researching all major cross-platform frameworks, Flutter was selected as the primary technology for LifeQuest. This document explains the reasoning, trade-offs, and full technology stack.

---

## Framework Comparison

| Criteria | Flutter | React Native | Native Swift | Kotlin Multiplatform |
|---|---|---|---|---|
| **iOS Performance** | Excellent | Very Good | Perfect | Good |
| **Android Performance** | Excellent | Very Good | N/A | Perfect |
| **UI Consistency** | Perfect (own renderer) | Good | Platform-native | Good |
| **Animation Quality** | Excellent | Good | Excellent | Good |
| **Development Speed** | Fast | Fast | Slow | Medium |
| **Code Reuse (iOS+Android)** | ~95% | ~85% | 0% | ~70% |
| **Community & Ecosystem** | Large | Very Large | Large | Growing |
| **Learning Curve** | Medium (Dart) | Low (JS) | Medium (Swift) | High |
| **App Size** | ~20MB+ | ~15MB+ | ~5MB+ | ~10MB+ |
| **Google Backing** | Yes | No | No | Yes (JetBrains) |
| **Best For** | Custom UI, animations | JS teams | iOS-only perfection | Shared logic only |

### Why Flutter Won

1. **Custom RPG UI requires pixel-perfect control** — Flutter's own rendering engine (Impeller) means the app looks identical on every device, which is critical for our gamified design
2. **Performance close to native** — Compiles directly to ARM machine code, no JavaScript bridge
3. **Single codebase for iOS + Android** — ~95% code reuse saves enormous time when we expand to Android
4. **Rich animation support** — XP bars, level-up celebrations, quest completion effects require smooth 60fps animations
5. **Growing ecosystem** — Flutter now powers apps for BMW, eBay Motors, Google Ads
6. **Hot Reload** — Near-instant development iteration

---

## Full Technology Stack

### Frontend (Mobile App)

| Layer | Technology | Purpose |
|---|---|---|
| **Framework** | Flutter 3.x | Cross-platform mobile UI |
| **Language** | Dart 3.x | Type-safe, modern language |
| **State Management** | Riverpod 2.x | Reactive state, dependency injection |
| **Navigation** | GoRouter | Declarative routing |
| **Local Storage** | Hive / Isar | Fast NoSQL local database |
| **Animations** | Rive + Flutter Animate | Character animations, XP effects |
| **HTTP Client** | Dio | API calls with interceptors |
| **Notifications** | flutter_local_notifications | Daily quest reminders |
| **Payments** | RevenueCat Flutter SDK | Subscription management |

### Backend & Infrastructure

| Layer | Technology | Purpose |
|---|---|---|
| **Backend-as-a-Service** | Firebase | Auth, Firestore DB, Cloud Functions |
| **Database** | Cloud Firestore | User data, quests, XP history |
| **Authentication** | Firebase Auth | Apple Sign-In, Google, Email |
| **Cloud Functions** | Firebase Functions (Node.js) | AI quest generation, scheduled tasks |
| **Storage** | Firebase Storage | User avatars, achievement images |
| **Analytics** | Firebase Analytics + Mixpanel | User behavior tracking |
| **Crash Reporting** | Sentry | Error monitoring |
| **Push Notifications** | Firebase Cloud Messaging (FCM) | Streak reminders, achievements |

### AI / Intelligence

| Component | Technology | Purpose |
|---|---|---|
| **Primary AI Model** | OpenAI GPT-4o via API | Quest generation, mentor chat |
| **Fallback AI Model** | Anthropic Claude 3.5 Sonnet | Redundancy if OpenAI is down |
| **AI Orchestration** | Firebase Cloud Functions | Prompt engineering, context management |
| **User Context Store** | Firestore | Persistent AI memory per user |
| **Prompt Templates** | Custom (stored in Firestore) | Versioned, A/B testable prompts |

### DevOps & Tooling

| Tool | Purpose |
|---|---|
| **Version Control** | GitHub (this repo) |
| **CI/CD** | GitHub Actions + Fastlane |
| **Code Quality** | Flutter Analyze + Dart Format |
| **Testing** | Flutter Test + Integration Tests |
| **App Distribution (Beta)** | TestFlight (iOS) + Firebase App Distribution |
| **App Store Deployment** | Fastlane deliver |
| **Monitoring** | Firebase Performance + Sentry |
| **Design** | Figma |

### Third-Party Services

| Service | Purpose | Cost Model |
|---|---|---|
| **RevenueCat** | Subscription management | Free up to $2.5k MRR |
| **OpenAI API** | AI mentor (GPT-4o) | Pay per token (~$0.005/1k tokens) |
| **Firebase Spark** | Backend (free tier) | Free up to limits |
| **Sentry** | Error tracking | Free tier available |
| **Mixpanel** | Product analytics | Free up to 20M events/month |

---

## Architecture Pattern

```
Flutter App
├── Presentation Layer (Widgets, Screens)
├── Application Layer (Riverpod Providers, Use Cases)
├── Domain Layer (Entities, Repository Interfaces)
└── Data Layer (Firebase, OpenAI API, Local DB)
```

Pattern: **Clean Architecture** + **MVVM**
- Separation of concerns
- Fully testable
- Easy to swap providers (e.g., replace OpenAI with own model in the future)

---

## Minimum iOS Requirements

- **iOS Version:** 16.0+
- **Devices:** iPhone 12 and newer (for optimal performance)
- **Xcode Version:** 15.0+
- **macOS Required for Build:** Yes (macOS 13+)

---

## Estimated AI Cost Model

| Scenario | Tokens/Day/User | Cost/User/Month |
|---|---|---|
| Light user (3 quests/day) | ~2,000 tokens | ~$0.03 |
| Average user (8 quests/day) | ~5,000 tokens | ~$0.075 |
| Power user (15 quests/day) | ~10,000 tokens | ~$0.15 |

**At $7.99/month subscription:** AI costs represent ~1-2% of revenue at scale. Sustainable.

---

## Future Considerations

- **Custom fine-tuned model** once we have sufficient user data (Year 2+)
- **On-device AI** via Apple Neural Engine for offline support
- **Web version** using Flutter Web (same codebase, ~80% reuse)
- **Kotlin Multiplatform** for shared business logic when adding Android natively

---

*Decision signed off by: Hoffmannss*
*Next review: Post-MVP launch*
