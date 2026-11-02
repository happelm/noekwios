---
title: 'Demo 1 – Apple Business tour'
lab:
    title: 'Demo 1 – Apple Business tour'
    module: 'Trainer demos'
---

# Demo 1 – Apple Business tour

**Module:** M1 Apple Business and the three tokens (with Lab 1.1) · **Duration:** 10 min · **Device:** trainer browser

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show where the three connections live on the Apple side and how a device gets to Intune.

### Prepare

- Sign in to Apple Business with the trainer account before the session (two-factor prompt).
- Have the Intune tab open on the Apple enrollment page.

### Show

1. Apple Business → MDM servers: the Intune server, its token download and expiry.
2. Device assignment: a purchased or added device and the MDM server it's assigned to. Intune syncs the assignment, the device then shows under the enrollment program token.
3. Apps and Books: the location token and purchased licenses (Outlook, Teams, Edge, Authenticator, Company Portal).
4. Managed Apple Accounts: federation with Microsoft Entra ID and service access settings.
5. Back in Intune: APNs certificate (Apple Account, expiry), enrollment program token, VPP token – who owns what.

### Point out

- APNs expires after 365 days. Renew it with the **same** Apple Account – a new account means every device must re-enroll.
- Devices bought through Apple or an authorized reseller can be added to Apple Business automatically. Others need Apple Configurator.
- Service access needs ADE and iOS/iPadOS 17 or later.

<!-- VERIFY: current Apple Business menu names (MDM servers, Apps and Books, service access) before class – Apple renamed the portal in 2026. -->
