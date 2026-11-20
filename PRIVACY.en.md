# Privacy Policy — Husky Grid

[🇧🇷 Português](PRIVACY.md) • [🇺🇸 English](PRIVACY.en.md)

Last updated: November 2026.

This Privacy Policy explains how **Husky Grid** handles user data. Our core foundation is **transparency and strict data privacy compliance (including LGPD - Brazilian General Data Protection Law, Law No. 13,709/2018)**: Husky Grid is an account management and grid productivity tool, not an invasive data collection platform.

---

## 1. Game and Session Data (100% Local)

- **Zero Keylogging and Zero Password Harvesting:** Husky Grid does not intercept, record, capture, or transmit the login credentials, passwords, game keystrokes, or account actions you perform within grid sessions.
- **Strict Chromium Isolation & Storage:** Session cookies, local browser storage (`localStorage`, `sessionStorage`), cached assets, and database entries are stored solely on your local hard drive within each account's isolated Chromium partition.
- **Account Profiles & Grid Layouts:** Your account labels, dockview grid configurations, custom recipes, and Eco Mode preferences are stored locally on your machine via `electron-store`.

---

## 2. Cloud Communication and License Validation

Husky Grid initiates outbound connections to official backend servers strictly for account authentication and subscription tier management:

### Information Processed for Licensing:
When you log in to activate a Pro plan (or validate free tier capabilities), the following data is transmitted via encrypted HTTPS:
1. **Husky Grid Account Credentials (Email and Password):** Used exclusively to authenticate your identity against our API and determine your subscription tier.
2. **Anonymous Device Identifier (`DeviceId`):** A cryptographic hash derived from non-reversible hardware and operating system parameters to enforce our 2-active-device limit per subscription.
3. **Subscription Status:** Verification data received from our payment processing partner (Stripe) confirming whether an active tier is Free or Pro.

### Token Encryption at Rest:
Authentication tokens provided by our licensing backend are stored securely on your machine using your operating system’s native hardware-backed encryption APIs (`safeStorage` via Electron — DPAPI on Windows, Keychain on macOS, and Secret Service on Linux).

---

## 3. Data Protection, Email Privacy & LGPD Compliance

In full alignment with the **Brazilian General Data Protection Law (LGPD - Law No. 13,709/2018)** and international data protection standards:

- **Strict Non-Reuse of Email and Personal Data:** Your registered email address is collected solely for essential technical functions: authenticating your account, managing your software license, and delivering critical transactional notices (e.g., password resets). **Your email and personal data will NEVER be reused, sold, rented, leased, or shared with third parties or advertising brokers for marketing, spam, or user profiling.**
- **No Data Commercialization:** We do not monetize or sell user personal data or browsing behavior under any circumstances.
- **Data Minimization:** We collect only the absolute minimum data required to deliver and maintain the requested software services.
- **Data Subject Rights (LGPD Art. 18):** As a user, you hold complete rights to:
  1. Confirm the processing of your data.
  2. Request access to or correction of your registered information.
  3. Revoke consent and request the **permanent deletion** of your account and personal data from our licensing servers.

To exercise any of these rights, simply email us at `privacy@huskygrid.com`.

---

## 4. Telemetry and Analytics

- **No Invasive Activity Telemetry:** We do not track the URLs you visit, the in-game assets you interact with, or your session duration.
- **Release Update Queries:** When automatic update checks are enabled, the application contacts the public GitHub Releases API to detect newer builds. No identifiable user information is sent during these polling checks.

---

## 5. Network Destinations

The Husky Grid desktop client communicates exclusively with:
1. Third-party web destinations and games explicitly configured or navigated to by the user.
2. The official licensing backend (`https://husky-grid-backend.fly.dev` or configured official domain).
3. The official GitHub Releases endpoint for update metadata.

---

## 6. Data Deletion

- **Local Data:** To completely purge all local session data, cookies, and cached states, uninstall the application and delete the local configuration directory:
  - **Windows:** `%APPDATA%\husky-grid`
  - **Linux:** `~/.config/husky-grid`
- **Cloud/Account Data:** If you wish to delete your account and permanently erase your email from our licensing database, contact our privacy desk below.

---

## 7. Privacy Inquiries and Data Protection Officer (DPO)

For any inquiries or requests regarding data privacy, LGPD compliance, or account deletion, reach out to:
- **Privacy Email:** `privacy@huskygrid.com`
- **Issue Tracker:** [EdwilsonCruz/Husky-Grid-Releases/issues](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues)
