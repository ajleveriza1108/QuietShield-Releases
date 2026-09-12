# QuietShield Android 2.9.86 — Code412

## Google Play Diagnostics + Resilient Build Pipeline

### User-facing changes

- Added privacy-safe Google Play and network environment diagnostics for intermittent installer-check failures.
- Protection Health reports Play installer provenance, Play Store/Services state, captive portal, other VPN conflicts, Private DNS, and IPv4/IPv6 readiness.
- Retains corrected Private Browser Forward-after-Back behavior and actual Android user-added CA detection.
- Keeps exactly the newest 20 shipped in-app release logs. Failed updater-only Codes 406–411 are intentionally excluded from the shipped release-note set.

### Release engineering

- Corrected `PlayEnvironmentPolicy` visibility so public diagnostic snapshots no longer expose an internal type.
- Corrected the recommendation separator to a valid escaped Kotlin string (`"\\n\\n"`).
- The corrected diagnostics + policy + regression-test sources were compiled with a local Kotlin stub harness before this updater was packaged.

- PowerShell 7.x is accepted with a minimum of 7.6.5; 7.6.6 is supported.
- The project Gradle wrapper remains authoritative.
- Dependency resolution runs online first with bounded retry for transient DNS/repository failures.
- Verified cached/offline execution is only attempted as a fallback when the required plugin artifacts actually exist in the selected Gradle cache.
- `D:\Windows Development\Gradle` is detected and classified rather than blindly forced as `GRADLE_USER_HOME`.
- Android source is rolled back on pre-build/build failure, but a verified Android build is preserved if only repository publication fails.

### Google Play

- Automatic Protection / Installer Check: **ON**.
- Upload the Code412 AAB manually to Internal Testing.
- For the intermittent Google-generated “Something went wrong” dialog, use Google Play Console's **Previous protection** option for the next controlled Internal Testing comparison while leaving Automatic Protection enabled.

