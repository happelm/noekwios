---
title: 'Demo 6 – App protection on a corporate iPhone'
lab:
    title: 'Demo 6 – App protection on a corporate iPhone'
    module: 'Trainer demos'
---

# Demo 6 – App protection on a corporate iPhone

**Module:** M6 App protection (after Lab 2.2) · **Duration:** 10 min · **Device:** iPhone 14

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show that app protection keeps work data in managed apps, also on a corporate device.

### Prepare

- A participant APP policy (Lab 2.2) assigned to the demo user. Outlook signed in.

### Show

1. Open Outlook – no extra app PIN on the enrolled iPhone with `IntuneMAMUPN` (App PIN when device PIN is set = Not required).
2. Copy text from a work mail, paste into Notes – blocked. Paste into Teams or Edge – allowed.
3. Try to save an attachment to Files – blocked.
4. Intune: Apps → Monitor → App protection status for the user.

### Point out

- Device management controls the iPhone, app protection controls the data inside the app.
- Apps from the same publisher share one app PIN.

Sources: Learn – App protection policy settings for iOS; Configure Outlook for iOS (managed devices).

<!-- VERIFY: IntuneMAMUPN needed for Teams and Edge too – note on Lab 2.2. -->
