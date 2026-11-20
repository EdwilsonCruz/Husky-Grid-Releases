# Privacy Policy — Husky Grid

[🇧🇷 Português](PRIVACY.md) • [🇺🇸 English](README.en.md)

Last updated: November 2026.

This Privacy Policy explains how **Husky Grid** handles user data. Our core foundation is **transparency**: Husky Grid is an account management and grid productivity tool, not an invasive data collection platform.

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
1. **Husky Grid Account Credentials:** Your registered email and password (used exclusively to authenticate against our API).
2. **Anonymous Device Identifier (`DeviceId`):** A cryptographic hash derived from non-reversible hardware and operating system parameters to enforce our 2-active-device limit per subscription.
3. **Subscription Status:** Verification data received from our payment processing partner (Stripe) confirming whether an active tier is Free or Pro.

### Token Encryption at Rest:
Authentication tokens provided by our licensing backend are stored securely on your machine using your operating system’s native hardware-backed encryption APIs (`safeStorage` via Electron — DPAPI on Windows, Keychain on macOS, and Secret Service on Linux).

---

## 3. Telemetry and Analytics

- **No Invasive Activity Telemetry:** We do not track the URLs you visit, the in-game assets you interact with, or your session duration.
- **Release Update Queries:** When automatic update checks are enabled, the application contacts the public GitHub Releases API to detect newer builds. No identifiable user information is sent during these polling checks.

---

## 4. Network Destinations

The Husky Grid desktop client communicates exclusively with:
1. Third-party web destinations and games explicitly configured or navigated to by the user.
2. The official licensing backend (`https://husky-grid-backend.fly.dev` or configured official domain).
3. The official GitHub Releases endpoint for update metadata.

---

## 5. Data Deletion

To completely purge all local session data, cookies, and cached states:
- Simply uninstall the application and delete the local configuration directory:
  - **Windows:** `%APPDATA%\husky-grid`
  - **Linux:** `~/.config/husky-grid`

---

## 6. Privacy Inquiries

For questions or data handling concerns, please contact us at:
- **Email:** `privacy@huskygrid.com`
- **Issue Tracker:** [EdwilsonCruz/Husky-Grid-Releases/issues](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues)
