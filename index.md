# Math Gym — Privacy Policy

**Effective date:** 16 May 2026

This Privacy Policy describes how Math Gym ("we", "us", "the app") collects, uses, and protects your information when you use the iOS application.

## Who we are

Math Gym is an iOS math quiz app developed by Eugen Kowal as an independent solo developer.

**Contact:** [email us](mailto:eugenkowal88@gmail.com)

## What we collect

### Account information

- A unique anonymous Firebase ID is created on first launch — silent, no input required from you.
- If you choose to sign in: your email address and (optionally) the display name returned by Apple, Google, or your direct email/password registration.
- Your chosen display name and optional avatar image (only if you set them in Edit Profile).

### Game progress

- XP, level, current streak, longest streak, best scores per category and difficulty, completed quizzes, daily challenge results, and combo records.
- Always stored locally on your device. Backed up to Firebase Firestore for cross-device sync and leaderboards **only if you have signed in** with Apple, Google, or email/password.

### Subscription status

If you subscribe to Math Gym Premium, your device's local StoreKit data is the source of truth — your subscription works fully offline once active. If you are signed in (Apple, Google, or email/password), we also store a small **advisory cache** of your subscription status in Firestore so that a different device using the same account can immediately know you're a subscriber on first launch, before StoreKit finishes its initial refresh.

The cache contains four fields on your user document:

- `isPremium` — whether you currently have an active subscription
- `subscriptionPlan` — `"monthly"`, `"annual"`, or empty
- `subscriptionExpiresAt` — your next renewal or expiration date
- `subscribedAt` — when you first subscribed

These fields are derived from Apple's StoreKit. We do **not** receive or store any payment information from Apple — only the entitlement state your device computes locally. Apple is the source of truth in all cases; if the cache disagrees with StoreKit, your device trusts StoreKit.

### Notifications

If you enable daily reminder notifications during onboarding (or later in iOS Settings), Math Gym schedules a single repeating local notification at the time you choose. The reminder is generated and delivered **entirely on your device** — we do not send the notification from a server, and we do not collect any data about whether you opened it. You can disable notifications at any time in iOS Settings → Notifications → Math Gym.

### App preferences (stored locally only)

A few small settings live on your device only — never sent to our servers, never linked to your account:

- The UI language you pick during onboarding (or change later in Profile).
- Whether you've completed onboarding and the age-13 verification result.
- Whether you've enabled daily reminder notifications and the time you chose.
- Internal tutorial-state flags (which coachmarks you've already seen).
- A streak-freeze prompt timestamp.

These are stored using Apple's standard `UserDefaults` and SwiftData mechanisms in your app's sandbox. They're wiped if you uninstall the app, and they may be included in your iCloud Backup if you have iCloud Backup enabled — that backup is encrypted by Apple and not accessible to us.

### Crash and diagnostic data

- When the app crashes, Firebase Crashlytics collects: device model, OS version, the crash stack trace, and your Firebase user ID (so we can correlate the crash with a specific account if you report one to us).
- Collection happens automatically the next time you re-launch the app after a crash.
- Anonymous-only users are tagged with their anonymous Firebase ID; signed-in users are tagged with their persistent Firebase UID.

### Age verification

When you first launch the app, we ask your age once. We use the answer **only** to confirm that you are 13 or older. We do **not** store the number itself — only the result of that check (a yes/no flag stored locally on your device).

If you indicate you are under 13:
- You can keep playing Math Gym locally on your device.
- You cannot create an account, sign in, or appear on global leaderboards.
- Your progress stays on your device only and is never sent to our servers.

Reinstalling the app re-runs onboarding, including the age question.

### What we do NOT collect

- Location, contacts, microphone, camera, health data.
- Photos beyond the single avatar image you explicitly pick in Edit Profile. The iOS PhotosPicker runs sandboxed — we never see your photo library, only the one image you hand us.
- Tracking identifiers for advertising — no IDFA, no advertising ID. We do not show the iOS App Tracking Transparency prompt because we do not track you across other apps or websites.
- Browsing history, messages, or any data from other apps.
- Payment information — Apple handles all in-app purchases through StoreKit; we never see your card details.

## Why we collect it

| Data | Purpose |
| --- | --- |
| Anonymous Firebase ID | Identify your install so progress can sync across launches and (later) devices |
| Email and display name | Account recovery, cross-device sync, leaderboard identification |
| Game progress | Display your stats, power XP and leveling, populate global leaderboards (only if signed in) |
| Crash and diagnostic data | Diagnose and fix crashes from real users |
| Subscription status cache | Recognize you as a subscriber on a new device before StoreKit's first refresh completes; unlock Premium features without a wait |

We do not sell, rent, or trade your personal information. Ever.

## Legal basis for processing (GDPR)

If you are in the EU, UK, or Switzerland, we process your data on the following grounds:

- **Performance of a contract** — to provide the app's core functionality (your account, your saved progress, leaderboard participation).
- **Legitimate interests** — to diagnose crashes and improve the app (Firebase Crashlytics non-fatal logs and crash reports).
- **Consent** — for optional features like daily reminder notifications. You can revoke consent at any time in iOS Settings or by signing out in the app.

## Automated decision-making

We do not use your data for automated decision-making, profiling, or any process that produces legal or similarly significant effects on you. Your XP, level, streak, and leaderboard rank are gameplay scoring — not automated decisions in the legal sense.

## Third-party services we use

- **Firebase Authentication, Firestore, and Crashlytics** (Google LLC) — see [Google's Privacy Policy](https://policies.google.com/privacy).
- **Sign in with Apple** — see [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
- **Sign in with Google** — see [Google's Privacy Policy](https://policies.google.com/privacy).
- **Apple StoreKit / App Store** (Apple Inc.) — processes all in-app subscriptions and payment information. See [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).

These providers process your data under their own Data Processing Agreements. They may store data on servers located outside your country.

## Where data is stored

Firestore data is stored in Google's `eur3` (European multi-region) data centers, chosen for GDPR proximity. Crashlytics data is processed by Google globally.

## How long we keep it

We keep your data until you delete your account in the app or stop using the app. Anonymous accounts from uninstalled apps are retained indefinitely because we have no way to identify them as abandoned.

When you delete your account from inside the app, your local data is wiped immediately and the cloud copy in Firestore is removed within 30 days. Your subscription is **not** cancelled by account deletion — it continues to renew through Apple until you cancel it separately in iOS Settings → Apple ID → Subscriptions.

## Subscriptions and billing

Math Gym Premium is sold as an auto-renewing subscription through Apple's App Store. There are two plans:

- **Monthly:** $4.99 per month
- **Annual:** $29.99 per year, with a 7-day free trial for new subscribers

Premium unlocks Gold and Diamond difficulty tiers and applies a 1.5× XP multiplier to all sessions.

**How billing works.** Payment is charged to your Apple ID at the moment you confirm the purchase (or at the end of the free trial, if you started one). Your subscription auto-renews at the same price unless you cancel at least 24 hours before the end of the current period. Apple notifies you before each renewal. Any unused portion of a free trial is forfeited when you start a paid subscription.

**Cancelling.** You can cancel at any time in iOS Settings → tap your Apple ID at the top → Subscriptions → Math Gym → Cancel Subscription. Cancellation takes effect at the end of your current paid period — you keep Premium access until then. We never auto-cancel a subscription on your behalf, and we never charge fees outside the Apple-published price.

**Restoring purchases.** If you reinstall the app or sign in on a new device, tap "Restore Purchases" in the paywall or in your Profile to re-apply your active subscription. This calls Apple's `AppStore.sync()` to verify your purchase against the same Apple ID — no email or password is sent to us.

**Family Sharing.** Math Gym Premium is enabled for Apple Family Sharing. Up to six family members in your Family Sharing group share one paid subscription at no extra cost. Family Sharing is managed entirely by Apple's Family Sharing system; we receive only the entitlement, not the identities of the other family members.

**Payment information.** Apple handles your entire payment process: card details, billing address, tax, currency conversion, refunds, and renewal reminders. We do not see your card number, billing address, or any other payment information. Apple shares with our app only whether you currently have an active entitlement.

**Refunds.** All refund requests must go through Apple at [reportaproblem.apple.com](https://reportaproblem.apple.com). We cannot process refunds directly. If Apple grants a refund and revokes your entitlement, your Premium access ends and the cache described in **Subscription status** above is updated to match.

**Pricing.** Local currency conversion and regional price tiers are set by Apple. The prices above are the U.S. App Store prices; your local price may differ.

## Your rights

You can:

- **Access your data** — visible in the Profile tab inside the app.
- **Edit your data** — change your display name and avatar via Profile → Edit.
- **Delete your account and all associated data** — Profile tab → Manage account → Delete account. Local data is wiped immediately; the cloud copy is removed within 30 days. Deletion is irreversible.
- **Export your data** — [email us](mailto:eugenkowal88@gmail.com) and we will send you a copy within 30 days.
- **Withdraw consent** — sign out at any time. Your local data stays on your device until you uninstall.

We will not deny you service, charge different prices, or provide a degraded experience because you exercise any of these rights.

If you live in the EU, UK, or Switzerland, you have additional rights under GDPR including the right to lodge a complaint with your local data protection authority.

If you live in California, you have additional rights under the CCPA, including the right to request deletion and to opt out of the sale of personal information (we never sell personal information).

## Children's privacy

Math Gym is rated 12+. We do not knowingly collect data from children under 13. If you believe a child under 13 has used the app and provided us with personal information, [email us](mailto:eugenkowal88@gmail.com) and we will delete their data immediately.

## Security

We rely on Firebase's industry-standard infrastructure: TLS in transit, encryption at rest, and Firestore security rules that limit each user to reading and writing only their own data. The leaderboard collection is readable by all signed-in users but writable only by the owner of each entry.

No system is perfectly secure. We will notify affected users without undue delay if we become aware of a personal data breach that poses a risk to your rights and freedoms.

## Changes to this policy

We may update this policy from time to time. Material changes will be reflected by updating the "Effective date" above. Continued use of the app after a change constitutes acceptance.

## Contact

Questions, concerns, or requests: [email us](mailto:eugenkowal88@gmail.com).
