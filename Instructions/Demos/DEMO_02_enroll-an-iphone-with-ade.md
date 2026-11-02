---
title: 'Demo 2 – Enroll an iPhone with ADE'
lab:
    title: 'Demo 2 – Enroll an iPhone with ADE'
    module: 'Trainer demos'
---

# Demo 2 – Enroll an iPhone with ADE

**Module:** M2 Automated device enrollment (during or after Lab 1.2) · **Duration:** 20 min + reset time · **Device:** iPhone 14

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show a corporate iPhone from wipe to work-ready: Setup Assistant with modern authentication, Await final configuration, enrollment time grouping and JIT registration.

### Prepare

- iPhone assigned to the Intune MDM server in Apple Business and synced in Intune (enrollment program token → **Sync**).
- One enrollment policy assigned to the iPhone (from a participant's Lab 1.2, or the trainer's): Setup Assistant with modern authentication, Await final configuration, enrollment time grouping group.
- Back up anything you need from the iPhone. Start the wipe **before a break** – reset plus Setup Assistant takes a while.

### Show

1. Erase the iPhone (Settings → General → Transfer or Reset iPhone, or Intune **Wipe**).
2. Setup Assistant shows **Remote Management** – the device belongs to the organization.
3. Sign in with the Entra account in Setup Assistant.
4. Await final configuration: the device stays in Setup Assistant until the critical policies and apps are there.
5. Home screen: Company Portal and Authenticator arrive. Sign in to the first work app → JIT registration in Microsoft Entra ID.
6. Intune: device with ownership **Corporate**, **Supervised** = Yes, member of the enrollment time grouping group.
7. Entra: device object before and after the first app sign-in.

### Point out

- The legacy Setup Assistant authentication option is gone since 2610. Use Setup Assistant with modern authentication (or Company Portal).
- Each re-enrollment creates a new Entra device object – assigned group memberships are lost, enrollment time grouping adds it again.
- An enrollment restriction that blocks iOS for all users breaks ADE ("invalid profile"). Block only personally owned devices.

Sources: Learn – Set up just-in-time registration in Microsoft Intune; Enrollment time grouping in Microsoft Intune; Tutorial: Set up Intune enrollment for iOS/iPadOS devices in Apple Business.
