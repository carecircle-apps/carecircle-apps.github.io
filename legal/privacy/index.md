---
layout: default
permalink: /legal/privacy/
title: "Privacy Policy"
description: "How Juntos handles your data — what we collect, where it lives, and your rights over it."
---
**Updated: September 24, 2026**

Juntos is a family-led care coordination app built by Ricardo Ochoa. This Privacy Policy explains what information we collect, how we use it, where it lives, and your rights over it. It's written to be understood, not just to satisfy a checklist.

If you have questions, email **carecircle89@icloud.com**.

---

## What Juntos Is — and Isn't

Juntos helps families coordinate the care of a hospitalized or chronically ill loved one. Multiple family members can share patient context, log shifts, communicate, and use AI assistance to draft physician questions and family updates.

Juntos is intended for family coordination, not diagnosis, treatment or emergency response. It is not a healthcare provider. AI output can be wrong and does not replace advice from your loved one's healthcare team.

Juntos is intended for family care coordination, not as a clinical records system for healthcare providers. We do not currently offer Business Associate Agreements (BAAs). Healthcare organizations should not deploy the app for regulated clinical workflows without a separate assessment of their obligations and the service arrangements required.

---

## What We Collect

Juntos collects information in three categories.

### 1. Information you provide

- **Account info:** your name, email address, and password (stored hashed by Supabase Auth)
- **Patient information:** the patient's name, care type, medical history, current diagnoses, medications, symptoms, and any other context you choose to add
- **Shift logs:** vitals, mood, events, notes, follow-ups, and any other observations you record during a caregiving shift
- **Chat messages:** messages you send to other members of your care circle
- **Documents and scanned text:** text you import or save from a selected photo. Photo recognition runs on your device; saved text can become shared patient context.
- **AI conversations:** the questions you ask the AI features and the context provided to them

### 2. Service information

- **Authentication and security records:** our hosting and authentication providers process technical request information, such as IP addresses and request timestamps, to operate and secure the service.
- **AI usage and purchase records:** account-linked request identifiers, allowance counts, answer-source identifiers, latency and subscription information support limits, retries, billing and troubleshooting. These records are not anonymous screen-usage analytics.
- This version does not include a separate advertising, screen-tracking or crash-reporting SDK.

### 3. Information we do NOT collect

- We do not access your contacts, calendar, location, microphone, or camera unless you explicitly grant permission for a specific feature
- We do not collect health data from Apple Health or any external medical record
- We do not track you across other apps or websites
- We do not sell your data to anyone, ever, under any circumstances

---

## Where Your Data Lives

### Your device

Juntos keeps care records and app state in its private device storage. Some context-document fields use application-level encryption with a key stored in iOS Keychain; this does not mean that every cached field is separately encrypted by Juntos. Device operating-system protections also apply. Your device PIN is stored as a salted hash; authentication session tokens and encryption keys use Keychain. Your password is processed by the authentication service; this statement does not mean the app stores your password in Keychain.

The current iOS app excludes the app's Documents and Application Support folders from device backups. This does not remove copies from older backups or change backups of images already in your personal Photos library. Signing out clears Juntos's account data from the app using its local cleanup flow. Cloud data is managed separately.

### Cloud sync (Supabase)

If you create or join a care circle, the following is stored in our backend, hosted on **Supabase** (PostgreSQL + Auth, hosted in AWS us-east-2):

- Your name and email (in the `profiles` and `auth.users` tables)
- Care circle membership and role (caregiver or external family member)
- Invite codes
- Chat messages (in plaintext, protected by Row-Level Security policies)
- Recovery milestones
- Patient context documents (in plaintext at the backend, with caregiver access restricted by circle in the app)
- Shift schedules and assignments
- AI-extracted learnings

For the care-circle features described here, we use circle membership, roles, Postgres Row-Level Security and server-side authorization checks to restrict ordinary app access. Authorized backend services and administrators have separate operational access; circle permissions do not make the data unreadable to the service operator.

### AI processing (Anthropic Claude)

When you enable AI sharing and send a question, your question and selected care context pass through **Juntos's server** to **Anthropic's Claude API**. Ricardo Ochoa supplies the provider account; you do not need to supply an API key. This processing can include sensitive health information you have chosen to record. Only share information you are authorized to share.

- Questions may also be sent to Juntos's server for safety and reference-library lookups. General answers may be cached within your circle with their question text; patient-context answers bypass that cache. The cache is separate from the quota service's encrypted retry store.
- The current app does not automatically submit questions or AI answers to the general library-curation queue. Any older queued records require a separate retention review; they are not automatically published.
- The model receives the context selected for that request. It may not include every record; missing or outdated information can affect answers.
- Anthropic processes submitted data under its applicable commercial terms and [privacy policy](https://www.anthropic.com/legal/privacy).
- Juntos processes the request to provide the answer and enforce usage limits. The AI quota service does not retain plaintext prompts or context. Successful answers are encrypted for safe retries. Retry access expires after 24 hours. A scheduled cleanup removes expired encrypted retry answers from the active database; a service interruption can delay that cleanup. This is server encryption, not end-to-end encryption. Database backups may retain earlier encrypted copies under the hosting provider's backup retention. The app may separately retain answers in your conversation history.
- Account-linked usage records, request identifiers, and subscription status are used to prevent duplicate charges, enforce allowances, and control service costs. These records do not contain your prompt text.
- You can turn off AI sharing in AI options. This prevents future AI requests; it cannot recall information already processed. AI sharing consent is separate from purchasing a subscription.

Care coordination features can be used without enabling AI sharing. Older app versions allowed personal API keys. The updated app does not read or use those keys for AI requests.

### Apple subscriptions

Apple processes subscription payments. Juntos receives purchase identifiers, product and renewal/expiration information, and an account identifier linking a verified purchase to your Juntos account. We use Apple's signed transaction information to verify access and manage your question allowance. Juntos does not receive your full payment-card or bank details from Apple. Manage or cancel a subscription through your Apple account; deleting your Juntos account does not itself cancel an Apple subscription.

### Photos and document scanning

You choose which photos and files the app may read. Text recognition runs on the device; text you review and save becomes part of your care context and can be synced or used for an AI answer with your sharing permission. Local image references do not provide cross-device photo sharing. Juntos does not manage your personal iCloud Photos library. The updated import flow removes its own temporary picker copy when import or recognition finishes, including failure paths. It does not delete originals or blanket-delete other cached files. Cleanup of historical temporary copies remains under review.

---

## What We Use Your Data For

- **Provide the service:** show your patient information, sync across your devices, deliver chat messages
- **Enable family coordination:** display care circle members and their roles
- **AI assistance:** route your AI requests to Anthropic Claude with the relevant context
- **Troubleshooting:** service request status and timing help diagnose failures; the app does not claim that these account-linked records are anonymous
- **Security:** detect and prevent unauthorized access

We do not use your data for:
- Advertising of any kind
- Sale to third parties
- Training our own machine learning models (provider processing is described above)
- Profile-building
- Research without your explicit consent

---

## Your Rights

You can manage your account and permissions in the app, and request an export by email:

- **Export your data** by emailing carecircle89@icloud.com
- **Delete your account** via More → Security → Delete Account, or Account in family view. This removes your active sign-in identity, profile and memberships and starts local account cleanup. Shared circles and care history are preserved for remaining members; your account links are removed, but names or information written into shared text may remain. Other members’ accounts and contributions are not deleted. Apple subscriptions must be managed separately in Apple Subscriptions.
- **Sign out from any device** via More → Security → Sign Out.
- **Withdraw consent for AI processing** by switching off AI sharing in AI options.
- **Leave a care circle** without deleting your account, in More → Circle.

Depending on where you live and which laws apply, you may have rights to access, correct, obtain a copy of, or delete personal information, withdraw consent, or object to certain processing. Email carecircle89@icloud.com to make a request. We may need to verify your identity and authority without requesting unnecessary health information. We will respond within the applicable legal deadline and explain any permitted extension or limitation. This policy does not determine which jurisdictions' laws apply to every user.

---

## Children's Privacy

Juntos is intended for adults coordinating care for a loved one (who may be a child). The app is not directed at children under 13. Children may not create their own accounts. An authorized adult may record information about a child receiving care.

If your loved one is a minor, the responsible adult (parent, guardian, or healthcare surrogate) is the account holder and is responsible for the information shared in the care circle.

---

## Security

We use the following measures to protect your information:

- **Transport encryption:** the app uses HTTPS connections to its cloud and AI services.
- **Storage protection:** Supabase provides encryption at rest for hosted database storage. iOS Keychain protects the secrets stored in it. Other local app records use iOS app-storage protections, and selected context fields have additional application-level encryption; not every local field is separately encrypted by Juntos.
- **Authentication:** device-level PIN, optional Face ID / Touch ID, and Supabase email + password
- **Access controls:** database policies and server checks restrict ordinary app access by account, circle membership and role.
- **Administrative access:** authorized service operators can access hosted records for support and operations. Administrative access is separate from circle membership; we do not describe this as end-to-end encryption

No system is completely secure. If a security incident requires notification, we will notify affected people and authorities as required by the laws that apply. Applicable deadlines and obligations require review for each incident.

---

## Data Retention

- **Account data:** the in-app deletion action removes the active sign-in identity, profile and memberships. It does not immediately remove every record held by the service, hosting backups or provider logs.
- **Care circle data:** the current account-deletion flow preserves shared care history, including contributions from former members. Removing an account link does not remove names or health information written into shared text. We do not currently apply a fixed automatic age-based deletion period to those shared records. Contact carecircle89@icloud.com to request removal of personal information that remains; we will assess the request and explain its outcome under applicable law. Leaving a circle and signing out are separate actions.
- **Purchase and security records:** some purchase-ownership and anti-abuse records remain after account deletion. They are separate from your active sign-in account. We have not established a single automatic deletion period for every operational record; do not assume that account deletion erases all of them.
- **Provider systems and backups:** Supabase backups and logs, Anthropic processing records and Apple transaction records follow their applicable service arrangements. These copies can persist after a record is removed from the active app database. We do not promise a fixed deletion deadline for all provider-held copies.
- **Requests:** email carecircle89@icloud.com for access, correction or deletion requests, including questions about information retained after account deletion. We will evaluate the request, identify applicable legal obligations and explain any retention limitation. We do not need your app password or API credentials to receive a request.

---

## Changes to This Policy

We may update this policy as Juntos evolves and will show the effective date of each published version. Material changes require appropriate notice and, where required, renewed consent before the changed processing begins. A policy update does not by itself authorize a new use of sensitive information. Past published versions are kept in our public GitHub repository.

---

## Contact

Ricardo Ochoa
Email: **carecircle89@icloud.com**

For privacy-specific questions: **carecircle89@icloud.com**

---

*Cuidamos juntos.*
