---
layout: default
permalink: /legal/privacy/
title: "Privacy Policy"
description: "How CareCircle handles your data — what we collect, where it lives, and your rights over it."
---
**Last updated: November 14, 2026**

CareCircle is a family-led care coordination app built by Lifted Labs. This Privacy Policy explains what information we collect, how we use it, where it lives, and your rights over it. It's written to be understood, not just to satisfy a checklist.

If you have questions, email **support@carecircle.app**.

---

## What CareCircle Is — and Isn't

CareCircle helps families coordinate the care of a hospitalized or chronically ill loved one. Multiple family members can share patient context, log shifts, communicate, and use AI assistance to draft physician questions and family updates.

**CareCircle is not a medical device, and not a healthcare provider.** Nothing in CareCircle constitutes medical advice. Always defer to your loved one's healthcare team.

CareCircle does not currently sign Business Associate Agreements (BAAs) with healthcare providers and is not, by itself, HIPAA-covered. Families using CareCircle for their own loved one's care fall outside HIPAA's scope. If you are a healthcare provider considering using CareCircle on behalf of patients, contact us before deploying.

---

## What We Collect

CareCircle collects information in three categories.

### 1. Information you provide

- **Account info:** your name, email address, and password (stored hashed by Supabase Auth)
- **Patient information:** the patient's name, care type, medical history, current diagnoses, medications, symptoms, and any other context you choose to add
- **Shift logs:** vitals, mood, events, notes, follow-ups, and any other observations you record during a caregiving shift
- **Chat messages:** messages you send to other members of your care circle
- **Photos and documents:** any images or files you choose to attach (medical history documents, lab screenshots, wound photos, etc.)
- **AI conversations:** the questions you ask the AI features and the context provided to them

### 2. Information we collect automatically

- **Device-level data:** your iOS or Android device model, OS version, and app version, used only for crash diagnosis and not linked to your identity
- **Usage events:** which screens you visit and which features you use, in aggregate and anonymized, to help us understand which features matter

### 3. Information we do NOT collect

- We do not access your contacts, calendar, location, microphone, or camera unless you explicitly grant permission for a specific feature
- We do not collect health data from Apple Health or any external medical record
- We do not track you across other apps or websites
- We do not sell your data to anyone, ever, under any circumstances

---

## Where Your Data Lives

### Your device (iOS Keychain + on-device encrypted storage)

The following stays on your device, encrypted with AES-256 using a key in iOS Keychain that we cannot access:

- Your device PIN (hashed, salted)
- Your Anthropic Claude API key (if you provide one)
- Patient context documents (cached, even when synced to cloud)
- AI insights and learnings
- Chat history (cached)

If you sign out, this data is erased from the device.

### Cloud sync (Supabase)

If you create or join a care circle, the following is stored in our backend, hosted on **Supabase** (PostgreSQL + Auth, hosted in AWS us-east-2):

- Your name and email (in the `profiles` and `auth.users` tables)
- Care circle membership and role (caregiver or external family member)
- Invite codes
- Chat messages (in plaintext, protected by Row-Level Security policies)
- Recovery milestones
- Patient context documents (in plaintext, only readable by caregivers in the same circle)
- Shift schedules and assignments
- AI-extracted learnings

Each user can only read data from circles they belong to. We use Postgres Row-Level Security to enforce this at the database level, not just at the application level.

### AI processing (Anthropic Claude)

When you use AI features (Ask AI, Handoff Brief, Doctor Rounds Prep, etc.), CareCircle sends the relevant patient context to **Anthropic's Claude API** using **your own API key that you provide**. This means:

- Anthropic processes the data under their privacy policy (https://www.anthropic.com/legal/privacy)
- CareCircle never sees, stores, or has access to these AI conversations
- You are the data controller for AI calls; Anthropic is the processor
- You can stop AI processing at any time by removing your Claude API key from More → AI Key

You can also use CareCircle without AI features by simply not providing an API key.

### Apple iCloud (for photos)

Photos you attach in CareCircle are stored in your **iOS Photos library** (your own iCloud, if iCloud Photos is enabled). CareCircle stores only references to those photos, not the photo bytes themselves. We do not have access to your iCloud.

---

## What We Use Your Data For

- **Provide the service:** show your patient information, sync across your devices, deliver chat messages
- **Enable family coordination:** display care circle members and their roles
- **AI assistance:** route your AI requests to Anthropic Claude with the relevant context
- **Crash diagnosis:** when the app crashes, we collect anonymized stack traces (no personal data)
- **Security:** detect and prevent unauthorized access

We do not use your data for:
- Advertising of any kind
- Sale to third parties
- Training machine learning models
- Profile-building
- Research without your explicit consent

---

## Your Rights

You can, at any time, from inside the app:

- **Export your data** by emailing support@carecircle.app
- **Delete your account** via More → Security → Delete Account. This permanently erases your user record, your circle memberships, all chat messages you sent, all milestones you created, all patient context you uploaded, and all AI learnings tied to you. This action cannot be undone.
- **Sign out from any device** via More → Security → Sign Out. This clears your local cache, including your Claude API key and any cached patient data.
- **Withdraw consent for AI processing** by removing your Anthropic API key.
- **Leave a care circle** without deleting your account, in More → Circle.

For users in jurisdictions with specific privacy rights (California CCPA, EU GDPR, Washington MHMDA, etc.), you have additional rights including access, correction, portability, deletion, and the right to opt out of certain processing. Email support@carecircle.app with your request and we will respond within 30 days.

---

## Children's Privacy

CareCircle is intended for adults coordinating care for a loved one (who may be a child). The app is not directed at children under 13. We do not knowingly collect information from anyone under 13.

If your loved one is a minor, the responsible adult (parent, guardian, or healthcare surrogate) is the account holder and is responsible for the information shared in the care circle.

---

## Security

We use the following measures to protect your information:

- **Transport encryption:** all data is sent over TLS 1.2+
- **Storage encryption:** Supabase encrypts data at rest using AES-256. iOS Keychain encrypts on-device data
- **Authentication:** device-level PIN, optional Face ID / Touch ID, and Supabase email + password
- **Row-Level Security:** database-level access controls so users can only read data for circles they belong to
- **Limited employee access:** no Lifted Labs employee has routine access to your personal data; access is logged and audited

No system is 100% secure. If we discover a data breach, we will notify affected users within 60 days as required by the FTC Health Breach Notification Rule.

---

## Data Retention

- **Account data:** retained as long as your account exists. Deleted within 30 days of account deletion.
- **Care circle data:** retained as long as the circle exists. When the last caregiver deletes their account, the circle and its data are deleted.
- **Crash logs:** retained for 90 days.
- **Anonymized usage events:** retained for 24 months.

---

## Changes to This Policy

We may update this policy as CareCircle evolves. We will notify you in the app of material changes. Continued use after a change means you accept the updated policy. Past versions are kept in our public GitHub repository for transparency.

---

## Contact

Lifted Labs LLC
Email: **support@carecircle.app**

For privacy-specific questions: **privacy@carecircle.app**

---

*Adelante. 💛*
