<!-- QUIETSHIELD_CURRENT_ANDROID_START -->
## Current Android phone/tablet manual build — 2.9.70 / Code396

**Competitive Hardening Foundation + Network Inspector v3**

- Google Play remains the customer in-app update channel for Code369+.
- Manual signed APK: [QuietShield-Premium-v2.9.70-Code396.apk](https://github.com/ajleveriza1108/QuietShield-Releases/releases/download/android-v2.9.70-code396-manual/QuietShield-Premium-v2.9.70-Code396.apk)
- APK SHA-256: **7c9d7b522cf4ff7e5eccc6ce7ce4ff326f8a6a9a368a8a29bd09242c98ff382c**
- Release record: [android-v2.9.70-code396-manual](https://github.com/ajleveriza1108/QuietShield-Releases/releases/tag/android-v2.9.70-code396-manual)
- Detailed release notes: [releases/QUIETSHIELD-2.9.70-CODE396.md](releases/QUIETSHIELD-2.9.70-CODE396.md)
- Legacy **update.json** and **android/phone-tablet/latest.json** are intentionally unchanged.
<!-- QUIETSHIELD_CURRENT_ANDROID_END -->

# QuietShield Releases

Public update-delivery repository for QuietShield Premium on Android phones
and tablets.

This repository contains only:

- signed customer APK release assets,
- SHA-256 checksum files,
- update metadata,
- public release notes,
- buyer-facing update documentation.

The commercial Android source code is stored separately in the private
QuietShield-Android repository.

Android TV is not included in this repository workflow yet.

<!-- QUIETSHIELD_LATEST_START -->
## Latest release: QuietShield 2.5.6

- Version code: 281
- Release tag: v2.5.6
- Signed APK: QuietShield-Premium-v2.5.6-Final-Code281-R1.apk
- AAB: reserved for Play Console and not part of this Direct GitHub release
- APK SHA-256: 18a0f297f1159cb9b38ea5e57893276de3eb80e3301b13f20bc8e60525947d8f
- Revision: Final Code 281 R1
- Update path: existing Direct GitHub installations detect Code 281 through both verified updater files
- App Connection Lock: profile schedules, automatic reconnect, notifications, and transparent protection labels
- Mobile Data Watch: user/system/Google usage review with warnings and no automatic blocking
- Profile editor: digital-keyboard focus and cursor repair
- Private Browser: pull down to refresh while preserving browsing data and tabs
- Retained limitations: PiP removed, Smart Skip Beta, website controls may require future compatibility maintenance

<!-- QS-CODE397-PLAY-STARTUP:START -->
## Current Android critical hotfix — 2.9.71 / Code397

The manual Code397 APK removes automatic Google Play update calls from QuietShield startup.

APK SHA-256:
1f5f08ac529bec33be5fa2e495d5513ad6d92767c9d9a892ce9295d8bb1e0916

For Google Play Internal Testing, Automatic protection must be turned off for this release before rollout.
<!-- QS-CODE397-PLAY-STARTUP:END -->

<!-- QS-CODE398-PREMIUM-CRASH:START -->
## Current Android critical fix — 2.9.72 / Code398

Fixes the PremiumActivity `ScrollView can host only one direct child` crash
observed during activity resume on Android 16.
<!-- QS-CODE398-PREMIUM-CRASH:END -->

<!-- QS-CODE399-PREMIUM-LIFECYCLE:START -->
## Current Android fix — 2.9.73 / Code399

Fixes repeated Premium screen crash caused by rebuilding its ScrollView hierarchy
during Activity resume.
<!-- QS-CODE399-PREMIUM-LIFECYCLE:END -->

<!-- QS-CODE400-PREMIUM-SCROLL:START -->
## Current Android fix — 2.9.74 / Code400

Fixes the confirmed Premium screen ScrollView direct-child crash.
<!-- QS-CODE400-PREMIUM-SCROLL:END -->
