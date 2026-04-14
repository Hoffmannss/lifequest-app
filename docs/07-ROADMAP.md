# 07 — Product Roadmap

**Last Updated:** April 2026
**Methodology:** Iterative releases, user-feedback driven

---

## Overview

```
Phase 0: Pre-construction (NOW)     → Done when this repo is complete
Phase 1: MVP Build (Q2-Q3 2026)     → Core features, iOS only
Phase 2: Beta Launch (Q3 2026)      → TestFlight, 100 beta users
Phase 3: App Store Launch (Q4 2026) → Public iOS launch
Phase 4: Growth (Q1 2027)           → Marketing, user acquisition
Phase 5: Android (Q2 2027)          → Play Store launch
```

---

## Phase 0 — Pre-Construction
**Timeline:** April 2026 (current)
**Status:** In Progress

### Deliverables
- [x] Concept document
- [x] Product Requirements Document (PRD)
- [x] Tech stack decision
- [x] System architecture
- [x] User personas
- [x] Monetization model
- [x] Roadmap (this document)
- [ ] Legal documents (Privacy Policy, Terms)
- [ ] Branding (name, colors, typography)
- [ ] Figma wireframes (lo-fi)
- [ ] Development environment setup
- [ ] GitHub repository structure

---

## Phase 1 — MVP Build
**Timeline:** May — August 2026 (4 months)
**Goal:** Working app with core loop

### Sprint 1 (May 2026) — Foundation
- [ ] Flutter project setup with Clean Architecture
- [ ] Firebase integration (Auth, Firestore)
- [ ] User authentication (Apple Sign-In + Email)
- [ ] Basic navigation and routing
- [ ] Design system implementation (colors, fonts, components)

### Sprint 2 (June 2026) — Core Game Loop
- [ ] Skill creation and management
- [ ] Quest data model and Firestore integration
- [ ] XP system and leveling algorithm
- [ ] Basic quest completion with animations
- [ ] Streak tracking system

### Sprint 3 (July 2026) — AI Integration
- [ ] Firebase Cloud Functions setup
- [ ] OpenAI API integration
- [ ] AI quest generation for new skills
- [ ] Daily quest regeneration (midnight cron)
- [ ] AI mentor chat interface

### Sprint 4 (August 2026) — Polish & Complete
- [ ] Onboarding flow with AI profiling
- [ ] Achievements system (50 achievements)
- [ ] Progress history and charts
- [ ] Push notifications
- [ ] RevenueCat integration (payments)
- [ ] App Store assets (screenshots, description)

---

## Phase 2 — Beta Launch
**Timeline:** September 2026
**Goal:** 100 beta users, gather feedback, fix critical bugs

### Deliverables
- [ ] TestFlight distribution
- [ ] Onboard 100 beta users (friends, community, social media)
- [ ] Analytics setup (Firebase + Mixpanel)
- [ ] Crash monitoring (Sentry)
- [ ] User interviews (min 10 interviews)
- [ ] Iterate based on feedback
- [ ] Performance testing on multiple devices
- [ ] Privacy Policy and Terms of Service published

### Beta Success Criteria
- Day-7 retention > 25%
- Average session > 5 min
- NPS score > 40
- < 1 critical bug per 100 sessions

---

## Phase 3 — App Store Launch (iOS)
**Timeline:** October—November 2026
**Goal:** Public launch, first paying customers

### Deliverables
- [ ] App Store submission
- [ ] App Store Optimization (ASO) — keywords, screenshots
- [ ] Press kit and landing page
- [ ] Social media presence (Instagram, TikTok, YouTube shorts)
- [ ] Launch day campaign
- [ ] PR outreach (tech blogs, productivity influencers)

### Launch Success Criteria
- 1,000 downloads in first week
- App Store rating ≥ 4.5 stars
- 50+ premium subscribers in first month

---

## Phase 4 — Growth & Optimization
**Timeline:** December 2026 — March 2027
**Goal:** Scale to 10,000 active users

### Features to Add
- [ ] Social sharing (achievements, skill milestones)
- [ ] Referral program ("Invite a friend, get 1 month Pro")
- [ ] Apple Watch companion app
- [ ] Widget support (iOS 16+ home screen widgets)
- [ ] Quest feedback loop ("Was this too easy/hard?")
- [ ] Localization: English, Portuguese, Spanish
- [ ] User-requested skill categories

### Marketing Channels
- Organic: TikTok/YouTube Shorts (productivity/self-improvement niche)
- Paid: Apple Search Ads
- Community: Reddit (r/selfimprovement, r/productivity), Discord
- Influencers: Brazilian productivity/lifestyle creators

---

## Phase 5 — Android Launch
**Timeline:** April—June 2027
**Goal:** Play Store launch, double addressable market

### Why Flutter Makes This Easy
- ~95% code reuse from iOS version
- Main additional work: platform-specific UI tweaks, Play Store assets
- Google Play billing integration (vs Apple IAP)
- Firebase already cross-platform

### Deliverables
- [ ] Android-specific UI adjustments (Material Design guidelines)
- [ ] Google Play billing integration
- [ ] Play Store submission
- [ ] Android-specific testing (device fragmentation)

---

## v2.0 Vision (2027+)

### Features Planned
- **Offline AI Mode** — on-device model via Apple Neural Engine
- **Social Quests** — challenge friends, guild system
- **Quest Marketplace** — community-created quest packs
- **AI Voice Coach** — audio-guided practice sessions
- **Custom Skill Builder** — users define their own skill categories
- **Skill Certificates** — shareable PDF proof of achievement
- **Web Version** — Flutter Web for desktop access
- **API / Integrations** — Spotify (music practice), Strava (fitness)

---

## Risk Register

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| App Store rejection | Medium | High | Review guidelines thoroughly before submission |
| OpenAI API cost spike | Low | Medium | Implement caching, rate limiting, fallback to Claude |
| Low D7 retention | Medium | High | Extensive beta testing, iterate before launch |
| Firebase costs scale | Low | Medium | Monitor usage, optimize queries |
| Competitor launches similar app | Medium | Medium | Speed to market, brand loyalty, unique AI quality |
| Solo dev burnout | Medium | High | Scope MVP tightly, ship early |

---

*Roadmap is a living document — updated monthly*
*Owner: Hoffmannss*
