---
title: 'Demo 5 – Apps and app configuration on the iPhone'
lab:
    title: 'Demo 5 – Apps and app configuration on the iPhone'
    module: 'Trainer demos'
---

# Demo 5 – Apps and app configuration on the iPhone

**Module:** M5 Apps and VPP (after Lab 2.1) · **Duration:** 10 min · **Device:** iPhone 14

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show VPP device-licensed apps and the app configuration from Lab 2.1 on a real device.

### Prepare

- Required VPP apps (Outlook, Edge) and the participant app configurations assigned to the demo iPhone group. Sync the device.

### Show

1. Apps install without an Apple Account prompt (device licensing).
2. Outlook: only the work account is allowed (`IntuneMAMAllowedAccountsOnly`, `IntuneMAMUPN`).
3. Edge: homepage shortcut URL and managed bookmarks.
4. Intune: app install status for the device, VPP licenses used/owned.
5. Edge `about:intunehelp` → **Get Started** → **Share Logs** → search `AppConfig` in `IntuneMAMDiagnostics.txt`.

### Point out

- **Uninstall on device removal** decides whether VPP apps stay when the device leaves management.
- DDM management type for VPP apps: iOS 18 or later, Required/Uninstall only, no app configuration.

Sources: Learn – Manage Apple volume-purchased apps; Assign apps to groups; App configuration policies – Diagnostic logs.
