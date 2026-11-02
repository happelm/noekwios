---
title: 'Lab 1.4 – Update policies with DDM'
lab:
    title: 'Lab 1.4 – Update policies with DDM'
    module: 'Day 1 – Get corporate iPhones into Intune'
---

# Lab 1.4 – Update policies with DDM

**Estimated time:** 20 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Keep corporate iPhones current: a pilot group gets the latest version after 3 days, production after 14 days.

**Why:** Since the October 2026 (2610) service release, iOS updates are managed only with declarative device management (DDM). The legacy update policies are gone.

1. Intune admin center → Devices → Configuration → **Create** → **New policy** → **iOS/iPadOS** → **Settings catalog**: `studentX iOS Update Pilot`. Add settings → **Declarative Device Management** → **Software Update Enforce Latest**:

   | Setting | Value |
   |---|---|
   | Delay in Days | 3 |
   | Install Time | `20:00` |

   Create it without assignment.
2. Same for `studentX iOS Update Production` with **Delay in Days** `14`. Assign it to `studentXdevices`.
3. Look at **Declarative Device Management** → **Software Update** (targeted version): **Target OS Version**, **Target Build Version**, **Target Date Time**, **Details URL**. Don't create it.
4. Settings catalog: `studentX iOS Update Settings` → **Declarative Device Management** → **Software Update Settings**. Look at deferrals, notifications and automatic actions. Create it without assignment.

### Checkpoint

- [ ] Two enforcement policies exist, production is assigned
- [ ] You can explain why "Success" in the policy report doesn't mean the update is installed

**Note:** When an enforcement is assigned, the device ignores Software Update Settings such as automatic actions.

**Note:** At the targeted deadline the user gets a one-minute countdown, then the device installs and restarts. A device that was off gets one hour after power-on.

**Note:** The policy report shows whether the declaration was installed. Check the OS version of the devices. After a device passed the target version, an old targeted policy reports an error – remove it.
<!-- Source: Learn "Configure update policies for Apple devices" (2026-11-02), MC1470869. VERIFY: label "Software Update Enforce Latest" in the portal and the Apple update report names under Devices → Monitor. -->
