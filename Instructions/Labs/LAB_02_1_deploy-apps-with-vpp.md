---
title: 'Lab 2.1 – Deploy apps with VPP and app configuration'
lab:
    title: 'Lab 2.1 – Deploy apps with VPP and app configuration'
    module: 'Day 2 – Run the fleet'
---

# Lab 2.1 – Deploy apps with VPP and app configuration

**Estimated time:** 30 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Install the standard apps silently on corporate iPhones and preconfigure Outlook and Edge.

**Why:** With VPP device licensing, apps install without an Apple Account on the device – the standard for corporate iPhones.

## VPP apps

1. Intune admin center → Apps → **iOS/iPadOS**. Find the apps that come from the VPP token (app type **iOS volume purchase program app**). Open Microsoft Outlook and look at **App licenses**: owned and used.
2. Assign **Microsoft Outlook**, **Microsoft Edge** and **Microsoft Authenticator** as **Required** to `studentXdevices`:

   | Setting | Value |
   |---|---|
   | License type | Device licensing |
   | Uninstall on device removal | Yes |

## App configuration for managed devices

3. Apps → Configuration → **Create** → **Managed devices**: `studentX iOS Outlook Config`, platform **iOS/iPadOS**, app **Microsoft Outlook**. Configuration designer:

   | Configuration key | Value type | Configuration value |
   |---|---|---|
   | `IntuneMAMAllowedAccountsOnly` | String | `Enabled` |
   | `IntuneMAMUPN` | String | `{{userprincipalname}}` |

   Assign to `studentXdevices`.
4. Apps → Configuration → **Create** → **Managed apps**: `studentX iOS Edge Config`, app **Microsoft Edge**. **Edge configuration settings**:

   | Setting | Value |
   |---|---|
   | Homepage shortcut URL | `https://portal.manage.microsoft.com` |
   | Managed bookmarks | `Company Portal` – `https://portal.manage.microsoft.com` |

   Assign to `studentXusers`.

### Checkpoint

- [ ] Outlook, Edge and Authenticator are required with device licensing
- [ ] Outlook allows only the work account, Edge shows the homepage shortcut (trainer device)

**Note:** `IntuneMAMAllowedAccountsOnly` with `IntuneMAMUPN` blocks personal accounts in Outlook, Edge, Teams and the Office apps on enrolled devices. Configuration keys are case sensitive.

**Note:** VPP apps can use the **DDM** management type on iOS/iPadOS 18 and later. With DDM, VPP apps can only be assigned as Required or Uninstall, and app configuration policies don't apply.

**Note:** Default for **Uninstall on device removal**: line-of-business apps Yes, store and VPP apps No.
<!-- Source: Learn configure-managed-ios (IntuneMAMAllowedAccountsOnly/IntuneMAMUPN), configure-edge-ios-android, manage-vpp-apple, assign-groups. VERIFY: which apps are bought in the demo VPP token; assignment of VPP apps by participants (scope tags). -->
