---
title: 'Demo 7 – Conditional Access for the iPhone'
lab:
    title: 'Demo 7 – Conditional Access for the iPhone'
    module: 'Trainer demos'
---

# Demo 7 – Conditional Access for the iPhone

**Module:** M7 Compliance and CA (with Lab 2.3) · **Duration:** 15 min · **Device:** iPhone 14 + trainer browser

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show the helpdesk path for "Outlook says I can't access company data".

### Prepare

- Compliance policy and a CA policy (report-only or on, only for the demo user) that require a compliant device for Office 365 on iOS.
- Emergency access accounts are excluded.

### Show

1. Make the iPhone noncompliant (for example raise the minimum OS version above the device's version, or require a longer passcode). Sync.
2. Intune: device → Device compliance → which setting fails.
3. Open Outlook – blocked or remediation prompt.
4. Entra: sign-in logs → the sign-in → **Conditional Access** tab (and **Report-only** tab).
5. What If: user, iOS, Office 365 – which policies apply.
6. Fix the setting, sync, show access again.

### Point out

- Most frequent causes on iPhones: device not registered (no JIT/Company Portal sign-in), noncompliant (OS version, passcode), wrong app.
- Report-only first, emergency access excluded, pilot before everybody.

Sources: Learn – Plan a Conditional Access deployment; Set up just-in-time registration in Microsoft Intune.
