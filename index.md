# Math Gym — Privacy Policy

**Effective date:** 26 April 2026

This Privacy Policy describes how Math Gym ("we", "us", "the app") collects, uses, and protects your information when you use the iOS application.

## Who we are

Math Gym is an iOS math quiz app developed by Eugen Kowal as an independent solo developer.

**Contact:** eugenkowal88@gmail.com

## What we collect

### Account information

- A unique anonymous Firebase ID is created on first launch — silent, no input required from you.
- If you choose to sign in: your email address and (optionally) the display name returned by Apple, Google, or your direct email/password registration.
- Your chosen display name and optional avatar image (only if you set them in Edit Profile).

### Game progress

- XP, level, current streak, longest streak, best scores per category and difficulty, completed quizzes, daily challenge results, and combo records.
- Always stored locally on your device. Backed up to Firebase Firestore for cross-device sync and leaderboards **only if you have signed in** with Apple, Google, or email/password.

### Crash and diagnostic data

- When the app crashes, Firebase Crashlytics collects: device model, OS version, the crash stack trace, and your Firebase user ID (so we can correlate the crash with a specific account if you report one to us).
- Collection happens automatically the next time you re-launch the app after a crash.
- Anonymous-only users are tagged with their anonymous Firebase ID; signed-in users are tagged with their persistent Firebase UID.

### What we do NOT collect

- Location, contacts, microphone, camera, health data.
- Photos beyond the single avatar image you explicitly pick in Edit Profile.
- Tracking identifiers for advertising — no IDFA, no advertising ID.
- Browsing history, messages, or any data from other apps.
- Payment information — Apple handles all in-app purchases through StoreKit; we never see your card details.

## Why we collect it

| Data | Purpose |
| --- | --- |
| Anonymous Firebase ID | Identify your install so progress can sync across launches and (later) devices |
| Email and display name | Account recovery, cross-device sync, leaderboard identification |
| Game progress | Display your stats, power XP and leveling, populate global leaderboards (only if signed in) |
| Crash and diagnostic data | Diagnose and fix crashes from real users |

We do not sell, rent, or trade your personal information. Ever.

## Third-party services we use

- **Firebase Authentication, Firestore, and Crashlytics** (Google LLC) — see [Google's Privacy Policy](https://policies.google.com/privacy).
- **Sign in with Apple** — see [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
- **Sign in with Google** — see [Google's Privacy Policy](https://policies.google.com/privacy).

These providers process your data under their own Data Processing Agreements. They may store data on servers located outside your country.

## Where data is stored

Firestore data is stored in Google's `eur3` (European multi-region) data centers, chosen for GDPR proximity. Crashlytics data is processed by Google globally.

## How long we keep it

We keep your data until you delete your account in the app or stop using the app. Anonymous accounts from uninstalled apps are retained indefinitely because we have no way to identify them as abandoned.

## Your rights

You can:

- **Access your data** — visible in the Profile tab inside the app.
- **Edit your data** — change your display name and avatar via Profile → Edit.
- **Delete your account and all associated data** — Profile tab → Manage account → Delete account. This is irreversible.
- **Export your data** — email us at eugenkowal88@gmail.com and we will send you a copy within 30 days.
- **Withdraw consent** — sign out at any time. Your local data stays on your device until you uninstall.

If you live in the EU, UK, or Switzerland, you have additional rights under GDPR including the right to lodge a complaint with your local data protection authority.

If you live in California, you have additional rights under the CCPA, including the right to request deletion and to opt out of the sale of personal information (we never sell personal information).

## Children's privacy

Math Gym is rated 12+. We do not knowingly collect data from children under 13. If you believe a child under 13 has used the app and provided us with personal information, contact us at eugenkowal88@gmail.com and we will delete their data immediately.

## Security

We rely on Firebase's industry-standard infrastructure: TLS in transit, encryption at rest, and Firestore security rules that limit each user to reading and writing only their own data. The leaderboard collection is readable by all signed-in users but writable only by the owner of each entry.

No system is perfectly secure. We will notify affected users without undue delay if we become aware of a personal data breach that poses a risk to your rights and freedoms.

## Changes to this policy

We may update this policy from time to time. Material changes will be reflected by updating the "Effective date" above. Continued use of the app after a change constitutes acceptance.

## Contact

Questions, concerns, requests:

**Email:** eugenkowal88@gmail.com
