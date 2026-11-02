---
title: 'Demo 4 – Software update with DDM'
lab:
    title: 'Demo 4 – Software update with DDM'
    module: 'Trainer demos'
---

# Demo 4 – Software update with DDM

**Module:** M4 Software updates with DDM (after Lab 1.4) · **Duration:** 10 min · **Device:** iPhone XR or iPad

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show the difference between "policy succeeded" and "update installed".

### Prepare

- An older iOS version on one trainer device, if available. Assign a Software Update Enforce Latest policy with a short delay, or a targeted Software Update with a near Target Date Time.

### Show

1. Intune: the policy report – declaration installed.
2. Device: Settings → General → Software Update – the enforced update.
3. Intune: device OS version – the real state.

### Point out

- At the targeted deadline the user gets a one-minute countdown, then the device installs and restarts. A device that was off gets one hour after power-on.
- When an enforcement is assigned, the device ignores Software Update Settings such as automatic actions.
- After a device passed the target version, an old targeted policy reports an error – remove it.

Sources: Learn – Configure update policies for Apple devices; MC1470869.

<!-- VERIFY: what the iPhone shows under Software Update while an enforcement is pending (wording, deadline display). -->
