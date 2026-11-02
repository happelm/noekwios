---
title: 'Lab 1.3 – Configure supervised iPhones'
lab:
    title: 'Lab 1.3 – Configure supervised iPhones'
    module: 'Day 1 – Get corporate iPhones into Intune'
---

# Lab 1.3 – Configure supervised iPhones

**Estimated time:** 40 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Build the baseline configuration for corporate, supervised iPhones.

**Why:** ADE devices are supervised. Many restrictions and device features work only on supervised devices.

Assign every profile to `studentXdevices`.

## Restrictions

1. Intune admin center → Devices → Configuration → **Create** → **New policy** → **iOS/iPadOS** → **Templates** → **Device restrictions**: `studentX iOS Restrictions`. Look at the three blocks: all enrollment types, device enrollment and ADE, ADE (supervised).
2. Configure:

   | Setting | Value |
   |---|---|
   | App Store, Doc Viewing, Gaming → Block viewing corporate documents in unmanaged apps | Yes |
   | Built-in Apps → Block removal of system apps from device | Yes |

## Device features

3. Create → **iOS/iPadOS** → Templates → **Device features**: `studentX iOS Lock Screen`. **Lock Screen Message**: asset tag `studentX` and footnote `If found, call +43 …`.
4. Create another **Device features** profile: `studentX iOS Home Screen`. **Home Screen Layout** → Dock: Outlook, Teams, Edge, Company Portal.

## Single sign-on

5. Create → **iOS/iPadOS** → Templates → **Device features**: `studentX iOS SSO Extension`. **Single sign-on app extension**:

   | Setting | Value |
   |---|---|
   | SSO app extension type | Microsoft Entra ID |
   | Enable shared device mode | Not configured |

## Wi-Fi

6. Create → **iOS/iPadOS** → Templates → **Wi-Fi**: `studentX iOS WiFi`, Wi-Fi type **Basic**, network name and SSID from the trainer, security type **WPA/WPA2-Personal**.

### Checkpoint

- [ ] Five profiles exist and are assigned to `studentXdevices`
- [ ] You can name two settings that need a supervised device

**Note:** The device restrictions template is no longer updated – new settings arrive in the settings catalog. The template is used here because it shows which enrollment type a setting needs.

**Note:** A home screen layout overwrites the user's layout. On personal corporate iPhones use the dock only, full layouts fit shared and kiosk devices (Day 2).

**Note:** The SSO app extension needs Microsoft Authenticator on the device (deployed in Lab 2.1). It's the base for just-in-time registration.

**Note:** Enterprise Wi-Fi with certificates needs a trusted certificate profile and a SCEP or PKCS profile – trainer demo.
<!-- VERIFY: exact setting labels (Lock Screen Message fields, SSO app extension type value "Microsoft Entra ID", Wi-Fi security type label) in the current portal. -->
