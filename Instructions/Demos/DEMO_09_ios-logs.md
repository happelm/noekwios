---
title: 'Demo 9 – iOS logs with the Mac Console and sysdiagnose'
lab:
    title: 'Demo 9 – iOS logs with the Mac Console and sysdiagnose'
    module: 'Trainer demos'
---

# Demo 9 – iOS logs with the Mac Console and sysdiagnose

**Module:** M9 Operations, reporting and troubleshooting (before Lab 2.4) · **Duration:** 15 min · **Device:** iPhone 14 + Mac (cable)

> **Draft:** This demo has not been run in this environment yet.

**Goal:** Show where iOS logs come from – and why a Mac at the helpdesk pays off.

**Why:** On iOS the Company Portal log has **no** information about Wi-Fi, VPN, SCEP or PKCS profiles. For these, Microsoft points to the device log in the Mac Console or a sysdiagnose.

## Which log for which problem

| Problem | Log | Where |
|---|---|---|
| Profile, Wi-Fi, VPN, SCEP/PKCS certificate doesn't arrive | Mac Console (live device log) | iPhone by cable on a Mac, Console app |
| Enrollment, Company Portal errors | Company Portal → **Send logs** (incident ID), or Console while reproducing | Device / Mac |
| App protection, app configuration | Edge `about:intunehelp` → **Share Logs** → `IntuneMAMDiagnostics.txt` | Device |
| App protection, remote | **Collect diagnostics** (Troubleshooting + support → Troubleshoot → user → Diagnostics), about 30 min | Intune admin center |
| SSO extension, sign-in | sysdiagnose, open in Console, filter `com.apple.appsso` (subsystem) | Device → Mac |
| Deep OS/MDM/DDM issue with an AppleCare case | **Trigger enhanced log collection** – supervised, iOS/iPadOS 27 or later, AppleCare token, logs go to the AppleCare case | Intune admin center → device → … |

## Part A – live log with the Mac Console

1. Connect the iPhone to the Mac with a cable. On the iPhone tap **Trust**.
2. Mac: Applications → Utilities → **Console**.
3. Under **Devices** select the iPhone → **Start**.
4. **Action** → **Include Info Messages** and **Include Debug Messages**.
5. **Clear**, empty the search box.
6. Assign a profile in Intune (for example a participant's lock screen message or Wi-Fi profile) and sync the iPhone.
7. Filter the Console. Microsoft's Wi-Fi example shows the process `profiled`:

   ```text
   profiled  Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM ...
   profiled  Profile "www.windowsintune.com.wifi.Contoso" installed.
   ```

   Search `process:profiled`, then the profile name. For VPN profiles search the VPN profile name.
8. Save: **Edit** → **Select All**, **Edit** → **Copy**, paste into TextEdit, **Format** → **Make Plain Text**, save as `.log`.

**Tip:** Assign a Wi-Fi profile that depends on a missing certificate profile. Intune only shows the state, the Console shows the reason.

## Part B – sysdiagnose from the iPhone

Use it when you can't reproduce the problem with the Mac attached. Create one before class – collection takes about 10 minutes.

1. Note the time.
2. Press **both volume buttons and the side button** at the same time and release after about 250 ms. Holding longer than about 1 second locks the device instead. iPhone vibrates briefly (iPad doesn't), a screenshot is taken.
3. Wait about 10 minutes.
4. Settings → Privacy & Security → Analytics & Improvements → **Analytics Data** → `sysdiagnose_YYYY.MM.DD_HH-MM-SS…`.
5. Share → **AirDrop** to the Mac.
6. Mac: extract the archive, open `system_logs.logarchive` – it opens in Console. For SSO search `com.apple.appsso` and set the filter type to **Subsystem**.

**More detail:** Apple offers logging profiles (`.mobileconfig`) for extra debug output, for example Managed Configuration, Wi-Fi, VPN, AppSSO, Enterprise SSO and Kerberos. Install the profile, reproduce the problem, then take a sysdiagnose.

## Without a Mac

- Settings → General → VPN & Device Management → management profile: which profiles and payloads are installed.
- Company Portal → **Send logs**: upload to Microsoft, incident ID for the support case.
- Edge `about:intunehelp`: app protection and app configuration.
- Authenticator → Send feedback → Having trouble → View diagnostic data.

## Sources

- Learn: [Retrieve iOS app logs from device](https://learn.microsoft.com/intune/user-help/diagnostics/collect-app-logs-ios)
- Learn: [Troubleshooting Wi-Fi device configuration profiles](https://learn.microsoft.com/troubleshoot/mem/intune/device-configuration/troubleshoot-wi-fi-profiles), [VPN profiles](https://learn.microsoft.com/troubleshoot/mem/intune/device-configuration/troubleshoot-vpn-profiles), [SCEP](https://learn.microsoft.com/troubleshoot/mem/intune/certificates/troubleshoot-scep-certificate-profiles), [PKCS](https://learn.microsoft.com/troubleshoot/mem/intune/certificates/troubleshoot-pkcs-certificate-profiles)
- Learn: [Troubleshooting the Microsoft Enterprise SSO Extension plugin on Apple devices](https://learn.microsoft.com/entra/identity/devices/troubleshoot-mac-sso-extension-plugin)
- Learn: [Device action: collect diagnostics](https://learn.microsoft.com/intune/device-management/actions/collect-diagnostics), [Device action: enhanced logging](https://learn.microsoft.com/intune/device-management/actions/apple-enhanced-logging)
- Learn: [App configuration policies – diagnostic logs](https://learn.microsoft.com/intune/app-management/configuration/overview#diagnostic-logs)
- Apple: [iOS sysdiagnose logging instructions](https://podcasters.apple.com/assets/iOS-sysdiagnose-logging-instructions.pdf), [Bug Reporting – Profiles and Logs](https://developer.apple.com/bug-reporting/profiles-and-logs/)

<!-- VERIFY: further iOS process names for MDM commands besides profiled. Learn's subsystem:com.apple.ManagedClient filter is documented for macOS only. Apple logging profiles: download needs an Apple developer sign-in?, profile lifetime per PDF. -->
