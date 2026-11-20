# Security Policy — Husky Grid

[🇧🇷 Português](SECURITY.md) • [🇺🇸 English](SECURITY.en.md)

This document outlines the security architecture, process isolation standards, and responsible vulnerability disclosure policy for **Husky Grid**.

---

## 1. Application Security Architecture

Husky Grid is built following the principle of least privilege and strict process isolation between host operating system capabilities and external web pages rendered inside grid panels.

### Chromium Partition Isolation
- Every game account or custom session in Husky Grid operates under a dedicated partition (`persist:husky-account-${accountId}`).
- Cookies, local storage (`localStorage`, `sessionStorage`), IndexedDB, and HTTP cache are strictly segmented by Chromium's core engine.
- Individual grid sessions cannot inspect, access, or modify session data or cookies belonging to other active accounts.

### Shell Security and Navigation Guards
- **Strict Content Security Policy (CSP):** Production shell web views enforce a rigid CSP (`script-src 'self'`), prohibiting unauthorized inline script execution and external script injection.
- **Hardware Permission Denial:** Sensitive host permissions — including camera, microphone, geolocation, and USB/Bluetooth access — are permanently denied by default (`denyPermissions`).
- **Safe Window Navigation:** Spawning arbitrary browser popup windows (`setWindowOpenHandler`) is rejected inside the client; verified external hyperlinks are securely handed off to the user's default system browser (`shell.openExternal`).
- **WebView Protection:** The `will-attach-webview` event is blocked to avert unauthorized guest webview attachments.

---

## 2. Binary Integrity and SHA-256 Verification

To guard against network tampering or corrupted downloads, each release published under the [Releases](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases) tab is accompanied by a cryptographic manifest: `SHA256SUMS.txt`.

### Windows Verification (PowerShell)
```powershell
Get-FileHash .\Husky-Grid-Setup-*.exe -Algorithm SHA256
```

### Linux Verification (Terminal)
```bash
sha256sum Husky-Grid-*.AppImage
# or for debian packages:
sha256sum husky-grid_*_amd64.deb
```

Compare your computed hash string against the matching entry inside `SHA256SUMS.txt`. If the hashes differ, **do not run the installer** and report the discrepancy immediately.

---

## 3. Operating System Warnings (Windows SmartScreen and Linux)

Our Windows binaries are packaged via electron-builder (NSIS). On new, standalone application releases distributed outside walled vendor app stores, Windows Defender SmartScreen may display an *"Unknown Publisher"* prompt.

- This alert reflects reputation-based telemetry algorithms maintained by Microsoft and does not indicate malicious code.
- We recommend verifying the binary's cryptographic SHA-256 hash before proceeding via *"More info" → "Run anyway"*.

---

## 4. Responsible Vulnerability Disclosure

If you discover a security flaw, permission leakage, or isolation bypass in Husky Grid, we ask that you disclose it responsibly and confidentially prior to any public disclosure:

1. **Contact Channel:** Send a technical briefing to `security@huskygrid.com` (or submit a private [GitHub Security Advisory](https://github.com/EdwilsonCruz/Husky-Grid-Releases/security/advisories)).
2. **Report Contents:**
   - Detailed description of the issue.
   - Tested Husky Grid version and target operating system.
   - Step-by-step reproduction instructions or a minimal Proof of Concept (PoC).
   - Assessed security impact (e.g., privilege escalation, session partition breakout).
3. **Our Response Commitment:**
   - We will acknowledge receipt of your disclosure within 48 business hours.
   - We will investigate and provide regular status updates until a patch is released.
   - Responsible reporters will be credited in the official release notes upon request.
