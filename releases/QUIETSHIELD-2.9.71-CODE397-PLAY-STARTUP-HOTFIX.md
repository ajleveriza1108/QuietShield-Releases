# QuietShield Android 2.9.71 — Code397

## Critical Google Play Startup Isolation Hotfix

### Fixed
- QuietShield no longer contacts Google Play update APIs while MainActivity is starting.
- Removed automatic AppUpdateScheduler scheduling from MainActivity.
- Removed automatic Play update refresh/coordinator calls from lifecycle startup.
- Manual App Updates remains available after the application has opened.
- Cached update attention may be displayed without contacting Google Play.
- Source is scanned for Play Integrity API and legacy Google Play Licensing startup gates.

### Android validation already completed
The exact APK/AAB published by this recovery package already passed:
- Debug Kotlin compilation
- Unit tests
- Release lint
- Signed APK build
- Signed AAB build
- APK signature verification

APK SHA-256:
1f5f08ac529bec33be5fa2e495d5513ad6d92767c9d9a892ce9295d8bb1e0916

AAB SHA-256:
eeaa5326995d201a9a9c3dc7bb1f20d8a023ca9f84dea748b88c70c69099d13c

### Mandatory Play Console setting
For the Internal Testing release, Google Play Automatic protection must be turned OFF for this release before rollout.

Google applies Automatic protection after AAB upload. An already Play-modified build cannot have that injected installer check removed by changing QuietShield source afterward.