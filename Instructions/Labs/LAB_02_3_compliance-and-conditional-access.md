---
title: 'Lab 2.3 – Compliance and Conditional Access for iPhones'
lab:
    title: 'Lab 2.3 – Compliance and Conditional Access for iPhones'
    module: 'Day 2 – Run the fleet'
---

# Lab 2.3 – Compliance and Conditional Access for iPhones

**Estimated time:** 35 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Allow company mail only from compliant iPhones – and test it without locking anyone out.

**Why:** Conditional Access sees compliance only for iPhones that are registered in Entra ID. Report-only mode shows the effect before it blocks anyone.

## Compliance

1. Intune admin center → Devices → Compliance → **Create policy** → **iOS/iPadOS**: `studentX iOS Compliance`:

   | Setting | Value |
   |---|---|
   | Device Health → Jailbroken devices | Block |
   | Device Properties → Minimum OS version | `18.0` |
   | System Security → Require a password to unlock mobile devices | Require |
   | System Security → Required password type | Numeric |
   | System Security → Minimum password length | 4 |
   | Actions for noncompliance → Mark device noncompliant | Immediately |

2. Assign to `studentXdevices`.

## Conditional Access

3. Entra admin center → Entra ID → Conditional Access → **Create new policy**: `studentX CA iOS Compliant Mail`:

   | Setting | Value |
   |---|---|
   | Users | `studentXusers`; exclude the emergency access group named by the trainer |
   | Target resources | Office 365 |
   | Conditions → Device platforms | Include **iOS** |
   | Grant | Require device to be marked as compliant |
   | Enable policy | **Report-only** |

4. Conditional Access → **What If**: user `studentX`, cloud app Office 365, device platform iOS. Which policies apply, which don't, and why?
5. Trainer demo: sign-in log of the demo iPhone → **Conditional Access** and **Report-only** tabs.

### Checkpoint

- [ ] `studentX iOS Compliance` is assigned
- [ ] `studentX CA iOS Compliant Mail` is in report-only
- [ ] You can explain the What If result

**Note:** Exclude emergency access accounts from every policy that blocks or restricts sign-in. Report-only policies don't need the exclusion.

**Note:** Minimum OS version `18.0`: Intune requires iOS/iPadOS 18 after the iOS 27 release (Message Center MC1454371).
<!-- VERIFY: CA rights for participants in the demo tenant. In the TS setup participants have no CA rights – then steps 3–4 become trainer demo and participants only read. -->
