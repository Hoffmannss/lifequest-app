# 11. Branding & Visual Identity — LifeQuest

> **Status:** Design brief — requires execution by UI/UX designer

---

## App Name

**LifeQuest**

- Short, memorable, and universally understood
- Conveys the idea of life as an ongoing adventure/journey
- Works well in English and Portuguese markets
- Domain suggestions: lifequest.app / getlifequest.com / lifequestapp.com

---

## Tagline Options

1. *"Turn your life into a game worth playing"*
2. *"Level up your life, one habit at a time"*
3. *"Your life. Your quest. Your progress."*
4. *"Make every day count"*

**Recommended:** Option 1 — most emotionally engaging and shareable

---

## Brand Personality

| Trait | Description |
|-------|-------------|
| Motivating | Encourages without being preachy |
| Playful | Game-like feel, but not childish |
| Empowering | User feels in control of their journey |
| Clean | Minimal UI, no visual noise |
| Trustworthy | Reliable data, honest communication |

---

## Color Palette

### Primary Colors

| Name | Hex | Usage |
|------|-----|-------|
| Quest Purple | `#6C3CE1` | Primary CTA, logo, key UI elements |
| Energy Cyan | `#00D4FF` | Highlights, streaks, level-up effects |
| Dark Void | `#0D0D1A` | Dark mode background |
| Pure White | `#FFFFFF` | Light mode background, text on dark |

### Secondary Colors

| Name | Hex | Usage |
|------|-----|-------|
| Success Green | `#2ECC71` | Completed quests, achievements |
| Warning Amber | `#F39C12` | Streak at risk, reminder alerts |
| Error Red | `#E74C3C` | Missed goals, critical alerts |
| Neutral Gray | `#8A8A9A` | Secondary text, disabled states |

---

## Typography

### Primary Font: **Inter** (Google Fonts — free)
- Headings: Inter Bold (700)
- Subheadings: Inter SemiBold (600)
- Body: Inter Regular (400)
- Captions: Inter Light (300)

### Accent Font: **Space Grotesk** (Google Fonts — free)
- Used for XP numbers, level badges, stats
- Reinforces the "game" aesthetic

### Font Sizes (Mobile)

| Element | Size |
|---------|------|
| H1 | 28px |
| H2 | 22px |
| H3 | 18px |
| Body | 15px |
| Caption | 12px |

---

## Logo Concept

### Symbol
- Geometric shield or hexagon with a stylized "L" or upward arrow
- Represents: protection, progress, achievement
- Should work in single color (for monochrome use)

### Logo Variants
1. **Full logo** — symbol + wordmark (horizontal)
2. **Compact** — symbol only (app icon, favicons)
3. **Dark version** — for light backgrounds
4. **Light version** — for dark backgrounds

### App Icon
- 1024x1024px master (Apple requirement)
- Rounded corners handled by OS
- No transparency
- Background: Quest Purple `#6C3CE1`
- Symbol: White or Cyan glow effect

---

## UI Design Principles

1. **Mobile-first** — every element designed for thumb navigation
2. **Dark mode default** — reduces eye strain, more gamey feel
3. **Light mode support** — accessibility requirement
4. **Micro-animations** — XP gains, level-up, streak fire effects
5. **Haptic feedback** — on achievement unlock, task completion
6. **Progressive disclosure** — don't overwhelm new users

---

## Iconography

- Style: Rounded, filled icons (not outline)
- Library: **Lucide Icons** or **Heroicons** (both open source)
- Custom icons needed for:
  - XP orb / experience point
  - Quest scroll
  - Level badge
  - Streak flame
  - Daily check-in coin

---

## Illustration Style

- Flat design with subtle gradients
- Characters: Abstract/geometric avatars (no realistic faces)
- Palette: Consistent with brand colors
- Scenes: Empty state illustrations, onboarding screens
- Resource: unDraw.co or LottieFiles for animated illustrations

---

## Motion & Animation

| Animation | Trigger | Duration |
|-----------|---------|----------|
| XP bar fill | Task completion | 600ms ease-out |
| Level-up explosion | Level threshold crossed | 1200ms |
| Streak flame pulse | Streak active | 800ms loop |
| Confetti burst | Achievement unlocked | 1500ms |
| Screen transitions | Navigation | 250ms slide |

- Implementation: Flutter's built-in AnimationController + Lottie package

---

## Voice & Tone

### In-App Copy Guidelines

| Context | Tone | Example |
|---------|------|---------|
| Onboarding | Warm, exciting | "Welcome, Hero. Your quest begins now." |
| Task reminder | Friendly nudge | "Your streak is waiting for you!" |
| Achievement | Celebratory | "Incredible! You just hit Level 10!" |
| Error | Calm, helpful | "Oops! Let's try that again." |
| Empty state | Motivating | "No quests yet — create your first one!" |

### Do's and Don'ts

**Do:**
- Use second person ("you", "your")
- Keep copy short and action-oriented
- Use positive framing

**Don't:**
- Use shame or guilt language
- Use jargon or technical terms
- Use exclamation marks excessively

---

## Brand Assets Checklist

- [ ] Logo (SVG + PNG variants)
- [ ] App icon (1024x1024px)
- [ ] Splash screen design
- [ ] Onboarding screens (3-5 slides)
- [ ] Color palette file (Figma/Sketch)
- [ ] Typography specimen
- [ ] Icon set (custom + library)
- [ ] Illustration pack
- [ ] Marketing banner templates (App Store / Play Store)
- [ ] Social media profile assets

---

## App Store Visual Requirements

### Apple App Store
- App Icon: 1024x1024px (no alpha)
- Screenshots: 6.7" (iPhone 15 Pro Max) — minimum 3, max 10
- App Preview Video: 15-30 seconds, .mov format
- Feature Graphic: Not required for iOS

### Google Play Store
- App Icon: 512x512px
- Feature Graphic: 1024x500px
- Screenshots: min 2, max 8 per device type
- Promo Video: YouTube URL

---

## Competitive Visual Analysis

| App | Visual Style | What to Learn |
|-----|-------------|---------------|
| Duolingo | Playful, green, cartoon owl | Mascots increase retention |
| Habitica | Pixel art RPG | Committed to game metaphor |
| Streaks | Minimal, circular | Clean = professional feel |
| Headspace | Soft pastels, characters | Calming, approachable palette |
| Notion | Ultra minimal, black/white | Clarity builds trust |

**LifeQuest differentiator:** Purple/dark game aesthetic + real progress data — serious about goals, fun in execution.

---

## Design Tools & Resources

| Tool | Purpose | Cost |
|------|---------|------|
| Figma | UI/UX design, prototyping | Free (Starter) |
| LottieFiles | Animated illustrations | Free tier |
| unDraw.co | SVG illustrations | Free |
| Lucide Icons | Icon library | Free/Open Source |
| Google Fonts | Typography | Free |
| Canva | Marketing materials | Free tier |
| Removebg | Background removal | Free tier |

---

*Brand identity to be finalized before first public beta release.*
