---
title: 'Lab 1.1 – Check the Apple connections'
lab:
    title: 'Lab 1.1 – Check the Apple connections'
    module: 'Day 1 – Get corporate iPhones into Intune'
---

# Lab 1.1 – Check the Apple connections

**Estimated time:** 15 minutes

> **Draft:** This lab is new and has not been run in this environment yet. If a step behaves differently, tell the trainer.

**Goal:** Find the Apple MDM push certificate, the automated device enrollment (ADE) token and the VPP token, and read who owns them and when they expire.

**Why:** All three connections exist once per tenant. If one expires, enrollment, management or app deployment stops for every Apple device.

1. Sign in to the Intune admin center with your `studentX` account.
2. Intune admin center → Devices → Enrollment → **Apple** → **Apple MDM Push certificate**. Note the Apple Account, the expiry date and the days until expiration.
3. Intune admin center → Devices → Enrollment → **Apple** → **Enrollment program tokens**. Open the token and note:

   | Setting | What to note |
   |---|---|
   | Expiration date | Renewal date |
   | Apple ID / account | Who renews it |
   | Devices | Serial numbers synced from Apple Business |
   | Enrollment policies | Which policy is the default |

4. Intune admin center → Tenant administration → Connectors and tokens → **Apple VPP tokens**. Note the country/region, the last sync and **Automatic app updates**.
5. Watch the trainer demo in Apple Business: MDM server, assigning a device to the MDM server, Apps and Books.

### Checkpoint

- [ ] You know the owner and expiry date of all three connections
- [ ] You can name what stops working when each one expires

**Note:** Renew the push certificate with **Renew** in the Apple Push Certificates Portal and the same Apple Account – never with **Create a Certificate**. A new certificate means every Apple device must enroll again.

**Note:** Use one company account that several admins can reach and renew all three connections on the same day.
<!-- VERIFY: read rights of Lab-Administrator for Students on enrollment program tokens and VPP tokens in the demo tenant. -->
