---
title: 'Lab 2.2 – App protection for corporate iPhones'
lab:
    title: 'Lab 2.2 – App protection for corporate iPhones'
    module: 'Day 2 – Run the fleet'
---

# Lab 2.2 – App protection for corporate iPhones

**Estimated time:** 25 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Keep company data inside the managed Microsoft apps on corporate iPhones.

**Why:** Device management controls the iPhone. App protection controls the work data inside an app – also when a user adds a private account or copies data to a private app.

1. Intune admin center → Apps → **Protection** → **Create policy** → **iOS/iPadOS**: `studentX iOS APP Core Apps`. Apps: **Core Microsoft apps**.
2. Data protection:

   | Setting | Value |
   |---|---|
   | Backup org data to iTunes and iCloud backups | Block |
   | Send org data to other apps | Policy managed apps |
   | Save copies of org data | Block |
   | Restrict cut, copy, and paste between other apps | Policy managed apps with paste in |
   | Org data notifications | Block org data |

3. Access requirements: **PIN for access** = Require, **App PIN when device PIN is set** = Not required.
4. Conditional launch: keep the defaults.
5. Assign to `studentXusers`.

### Checkpoint

- [ ] `studentX iOS APP Core Apps` exists and is assigned
- [ ] You can explain why the app PIN is skipped on the corporate iPhone

**Note:** **App PIN when device PIN is set = Not required** works only on enrolled devices that get `IntuneMAMUPN` through app configuration (Lab 2.1).

**Note:** Apps from the same publisher share one app PIN.
<!-- Based on MDDMI Lab 5.4 (tested), adapted for enrolled corporate devices. VERIFY: IntuneMAMUPN needed for Teams and Edge too – add configs if the trainer device asks for a PIN. -->
