# 08 — Legal Requirements

**Last Updated:** April 2026
**Disclaimer:** This document is for planning purposes. Consult a qualified attorney before launch.

---

## App Store Legal Requirements (Apple)

### 1. Apple Developer Program
- **Cost:** $99 USD/year (~R$550/year)
- **Enrollment:** individual or organization account
- **Required for:** TestFlight beta, App Store distribution
- **URL:** https://developer.apple.com/programs/

### 2. App Store Review Guidelines Compliance
All apps must comply with Apple's 5 guideline categories:

| Category | Key Requirements for LifeQuest |
|---|---|
| **Safety** | No harmful content; age rating must be accurate |
| **Performance** | App must be stable, fully functional at submission |
| **Business** | In-app purchases must use Apple IAP system |
| **Design** | Must follow Human Interface Guidelines (HIG) |
| **Legal** | Must have Privacy Policy; comply with all applicable laws |

### 3. Required Documents
- **Privacy Policy** — mandatory, must be linked in App Store listing AND accessible within app
- **Terms of Service** — strongly recommended, required for subscription apps
- **EULA (End User License Agreement)** — Apple's standard EULA applies by default, or you can provide custom

### 4. Privacy Manifest (Required as of April 2024)
Apple requires a `PrivacyInfo.xcprivacy` file that declares:
- What data types the app collects
- Why the data is collected
- Third-party SDK privacy practices
- API usage reasons (e.g., UserDefaults, FileTimestamp)

### 5. App Store Connect Requirements
- Age Rating questionnaire completed
- Export Compliance (encryption declaration)
- Screenshots for all required device sizes
- App Preview video (optional but recommended)
- Support URL and Marketing URL

---

## Brazilian Legal Requirements (LGPD)

**LGPD = Lei Geral de Proteção de Dados (Lei 13.709/2018)**
Brazil's equivalent of GDPR. Mandatory for any app collecting personal data from Brazilian users.

### Key LGPD Obligations

| Obligation | What LifeQuest Must Do |
|---|---|
| **Lawful Basis** | Obtain explicit consent for data collection during onboarding |
| **Data Minimization** | Only collect data necessary for the service |
| **Transparency** | Clear Privacy Policy explaining what data is collected and why |
| **User Rights** | Allow users to: view, correct, delete, export their data |
| **Data Controller** | Identify ourselves as the data controller in Privacy Policy |
| **Security** | Implement appropriate security measures (encryption, access control) |
| **Data Breach** | Notify ANPD and affected users within 2 business days of breach |
| **DPO** | Appoint a Data Protection Officer (can be the founder initially) |

### LGPD User Rights to Implement in App
- [ ] **Access:** User can download all their data (JSON export)
- [ ] **Correction:** User can edit their profile information
- [ ] **Deletion:** User can delete their account and all associated data
- [ ] **Portability:** Data export in machine-readable format
- [ ] **Revocation:** User can withdraw consent at any time

---

## International Legal Requirements

### GDPR (European Union)
Applies if any EU residents download the app.
- Similar to LGPD but stricter
- Requires Data Processing Agreement with processors (Firebase, OpenAI)
- Cookie consent (for web version)
- Right to be forgotten

### CCPA (California, USA)
Applies if California residents use the app AND:
- Revenue > $25M/year, OR
- Data from 50,000+ consumers, OR
- 50%+ revenue from selling personal data

For a new app, CCPA likely doesn't apply initially but Privacy Policy should include opt-out mechanism as best practice.

---

## AI-Specific Legal Considerations

### OpenAI Usage Policies
- Must comply with OpenAI's Terms of Service and Usage Policies
- Cannot use the API to violate users' privacy
- User conversations may be used by OpenAI to improve models (unless opting out via API settings)
- Must not store or share AI outputs that contain personal data beyond what's necessary

### AI Disclosure
- Recommended: Disclose to users that AI is powering recommendations
- Do NOT present AI advice as medical, legal, or financial advice
- Include disclaimer: "LifeQuest's AI mentor provides general guidance for personal development. It is not a substitute for professional advice."

---

## Subscription & Payment Legal Requirements

### Apple App Store
- All iOS subscriptions MUST use Apple In-App Purchase (not PayPal, Stripe, etc.)
- Apple takes 30% commission (15% for apps earning < $1M/year via Small Business Program)
- Must clearly display: price, billing period, cancellation policy
- Auto-renewal subscriptions require specific disclosure language
- Users can cancel via iOS Settings > Subscriptions

### Brazilian Consumer Law (CDC)
- 7-day cooling-off period for digital purchases (right to cancellation)
- Must honor this in subscription terms
- Clear refund policy required

---

## Business Registration (Brazil)

For commercial app sales, especially at scale:

| Option | Best For | Complexity |
|---|---|---|
| **CPF (individual)** | Early stage, low revenue | Low |
| **MEI** | Up to R$81k/year revenue | Low |
| **LTDA / SAS** | Scaling business, investors | Medium |

**Recommendation:** Start as MEI or individual, incorporate as SAS/LTDA when revenue justifies it or when seeking investment.

---

## Pre-Launch Legal Checklist

- [ ] Privacy Policy published (accessible URL)
- [ ] Terms of Service published
- [ ] Privacy Policy linked in App Store listing
- [ ] Privacy Manifest file (`PrivacyInfo.xcprivacy`) included in Xcode project
- [ ] Data deletion mechanism implemented in app
- [ ] Age rating correctly set in App Store Connect
- [ ] Export compliance declaration completed
- [ ] Subscription terms clearly displayed before purchase
- [ ] LGPD consent obtained during onboarding
- [ ] OpenAI API Terms of Service reviewed and complied with
- [ ] Support email set up and monitored

---

*This document is a planning guide, not legal advice.*
*Engage a Brazilian tech lawyer before App Store submission.*
*Recommended: conta.mobi or lawright.com.br for Brazilian startup legal services.*
