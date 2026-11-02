---
title: 'Lab 2.4 – Helpdesk cases'
lab:
    title: 'Lab 2.4 – Helpdesk cases'
    module: 'Day 2 – Run the fleet'
---

# Lab 2.4 – Helpdesk cases

**Estimated time:** 30 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Solve three helpdesk tickets on the trainer devices with the Intune and Entra admin centers.

**Why:** On iOS you can't open a log folder on the device. Most answers come from Intune, Entra sign-in logs and the device's own report.

Work in pairs. For every ticket write down **root cause**, **evidence** (where you saw it) and **fix**.

1. **Ticket 1:** "My new company iPhone has no Outlook." Start at the device in Intune → **Managed apps**, then the app assignment and the VPP licenses.
2. **Ticket 2:** "Outlook says I can't access company data." Start at Entra admin center → Sign-in logs → **Conditional Access**, then the device's compliance in Intune.
3. **Ticket 3:** "A returned iPhone asks for the previous user's Apple Account after the wipe." Which Intune device action helps, and what must be true for it?

### Checkpoint

- [ ] Root cause, evidence and fix for all three tickets

<details>
<summary>Hints</summary>

- Ticket 1: assignment group, license type, licenses used vs. owned.
- Ticket 2: is the device registered in Entra ID, and which compliance setting fails?
- Ticket 3: the device must be supervised.

</details>

**Note:** Users can upload logs from Company Portal (shake the device or More → Send Logs) and get an incident ID. Authenticator logs (SSO extension) are under Send feedback → Having trouble → View diagnostic data.
<!-- Trainer prepares the tickets on the demo devices. Solutions stay with the trainer. -->
