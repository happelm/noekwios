---
title: 'Lab 1.2 – Prepare automated device enrollment'
lab:
    title: 'Lab 1.2 – Prepare automated device enrollment'
    module: 'Day 1 – Get corporate iPhones into Intune'
---

# Lab 1.2 – Prepare automated device enrollment

**Estimated time:** 30 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Build an ADE enrollment policy for corporate iPhones with enrollment time grouping and Setup Assistant with modern authentication.

**Why:** The enrollment policy decides once, at the first start of the device, how it enrolls. Changes reach a device only after a factory reset.

## Enrollment time grouping

1. Entra admin center → Groups → `studentXdevices` → **Owners** → **Add owners**: search for the service principal **Intune Provisioning Client** (AppId `f1346770-5b25-470b-88bd-d5744ab7952c`; in some tenants it's named **Intune Autopilot ConfidentialClient**).

## Enrollment policy

2. Intune admin center → Devices → Enrollment → **Apple** → **Enrollment program tokens** → select the token → **Enrollment policies** → **Create policy** → **iOS/iPadOS**: name `studentX iOS ADE`.
3. **Device group**: `studentXdevices`.
4. Configuration settings:

   | Setting | Value |
   |---|---|
   | User affinity | Enroll with User Affinity |
   | Select where users must authenticate | Setup Assistant with modern authentication |
   | Await final configuration | Yes |
   | Locked enrollment | Yes |
   | Apply device name template | Yes – `studentX-{{SERIAL}}` |

5. Setup Assistant: hide the panes a corporate user doesn't need (for example Apple Pay, Siri, Screen Time). Keep **Location Services** and **Passcode**.
6. Create the policy. Don't assign devices – the trainer assigns the demo iPhone to one participant policy.

### Checkpoint

- [ ] `studentX iOS ADE` exists with `studentXdevices` as device group
- [ ] You can explain why Setup Assistant with modern authentication is used

**Note:** **Setup Assistant (legacy)** is no longer available since the October 2026 (2610) service release. Existing policies were switched to Setup Assistant with modern authentication.

**Note:** Microsoft recommends just-in-time (JIT) registration with Setup Assistant with modern authentication: the user registers the device in Entra ID in the first work app with the SSO app extension, not in Company Portal (Lab 1.3).

**Note:** Only static groups can be used for enrollment time grouping, and the group must be a scope group of your Intune role. Failures show in Devices → Monitor → **Enrollment time grouping failures**.
<!-- VERIFY: Lab-Administrator for Students needs Enrollment programs permissions incl. "enrollment time device membership assignment", and owner rights on studentXdevices (AU group admin). Device name template token {{SERIAL}} – check the exact token in the portal. Setup Assistant pane names. -->
