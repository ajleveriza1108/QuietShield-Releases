# QuietShield Android 2.9.70 — Code396

## Competitive Hardening Foundation + Network Inspector v3

**Release type:** Development / competitive hardening  
**Version:** 2.9.70  
**Version code:** 396  
**Base:** Code395 / 2.9.69 startup-safe lineage

### Active user-facing improvements

- Connection Explorer is upgraded to **Network Inspector v3**.
- A destination can now be copied directly from its detail view.
- Ads, ad-measurement endpoints, and tracker endpoints can be allowed for **10 minutes** as a browser-session compatibility test.
- Temporary compatibility allowances automatically expire and are never written as permanent browsing history.
- Temporary compatibility allowances **cannot override Threat, Child Safety, Imported, or explicit security rules**.
- Destinations can be added to the permanent website Allowlist or Blocklist directly from Network Inspector.
- Network Inspector never offers a permanent Allow action for Threat, Child Safety, Imported, or explicit Custom security categories.
- Permanent protection changes keep the existing administrator/parent authentication boundary.
- The compatibility assistant explains when a short allowance is appropriate instead of encouraging users to disable protection globally.

### Modern rule-engine foundation

Code396 adds an immutable domain-rule engine designed for large modern rule sets:

- exact domain and subdomain matching;
- wildcard-style domain rules;
- Adblock-style `||domain^` domain rules;
- allow rules using `@@`;
- rule action, category, source, rule text, and priority metadata;
- no linear full-list scan for each hostname decision;
- IDN/hostname normalization and validation;
- deterministic allow/block precedence.

This engine is introduced as a clean foundation. Existing verified QuietShield filtering remains authoritative until each VPN/DNS integration gate is completed and tested.

### DNS engine foundation

Adds typed DNS profiles and health/failover policies for:

- System DNS
- DNS-over-HTTPS (DoH)
- DNS-over-TLS (DoT)
- DNS-over-QUIC (DoQ)

The Code396 foundation includes:

- upstream identity and transport type;
- multiple-upstream profiles;
- latency/failure health snapshots;
- deterministic bounded failover;
- recovery after a successful upstream response.

**Important:** Code396 does not falsely claim that DoH/DoT/DoQ are already routing the device's VPN traffic. The transport models and failover engine are now cleanly testable and ready for service integration in the next gated networking tranche.

### Shared-IP attribution safety

Adds a time/TTL-aware connection-attribution index.

If multiple domains recently resolved to the same IP address, QuietShield will not pretend that the IP belongs to only one of them. This is foundational for avoiding false tracker attribution on CDNs and shared hosting.

### Filter-list update safety

Adds a staged update policy:

1. download candidate;
2. verify checksum;
3. parse and validate;
4. reject malformed candidates;
5. compile;
6. atomically replace the active set only after validation.

A bad or mostly-invalid list must never replace a working ruleset.

### Protection presets foundation

Introduces clean policy definitions for:

- Standard
- Strict
- Family
- Custom

The policy objects separate protection intent from UI switches so future screens do not duplicate rule logic.

### Performance regression gates

Adds a performance-budget policy for measuring regressions in:

- idle CPU;
- memory;
- DNS p95 latency;
- VPN recovery time.

The default policy flags regressions greater than 15% from a known baseline.

### Android 17 readiness foundation

Adds an explicit policy for local-network behavior when API/target 37+ is introduced.

This keeps LAN access changes visible instead of silently breaking printers, casting, NAS access, router administration, or other local-device workflows later.

### VPN coexistence foundation

Adds an explicit single-tunnel policy:

- QuietShield-only tunnel — supported;
- future WireGuard profile routed inside QuietShield — architecturally supported;
- unrelated external Android VpnService stacked transparently — not falsely reported as supported.

### OEM compatibility

Adds manufacturer-specific **help text only** for Samsung, HONOR/Huawei, Xiaomi/HyperOS, and OPPO/OnePlus/realme battery/background settings.

Core VPN/DNS behavior remains manufacturer-neutral. No OEM-specific networking branch is introduced.

### Retained Code395 safety

- Android 16 protected `BOOT_COMPLETED` rebroadcast crash remains fixed.
- `SystemStartupReceiver` remains removed.
- `BootReceiver` remains private and allowlisted.
- No Play Integrity or legacy Play Licensing hard-start gate is allowed.
- Google Play remains the in-app update channel.
- Existing VPN `SYSTEM_EXEMPTED` foreground-service contract remains required.
- Code394 explainable Connection Explorer evidence rules remain retained.

### Repository publication

The R1 package builds and verifies the signed AAB + APK **before** any repository mutation.

After all Android gates pass, the publisher:

- auto-detects the existing default branch of the private source repo;
- auto-detects the existing default branch of `QuietShield-Releases`;
- updates the source repository;
- removes stale `SystemStartupReceiver.kt` from the source repo if still present;
- updates both repository `README.md` managed sections;
- adds detailed Markdown release notes to both repositories;
- creates/updates the Code396 manual GitHub Release;
- uploads the signed Code396 APK and SHA-256 file;
- leaves legacy `update.json` and `android/phone-tablet/latest.json` untouched.

### Validation gates

- PowerShell 7.6.5 parser preflight
- complete package SHA-256 verification
- exact Code394/395/396 source-state detection
- idempotent Code396 reruns
- rollback-safe source mutation
- Kotlin compile
- all debug unit tests
- release lint
- signed AAB
- signed APK
- APK certificate verification
- Code393–396 What's New asset checks
- Code395 startup safety checks
- Play hard-start scan
- VPN foreground-service contract
- repository allowed-path staging guard
- legacy direct-update feed guard

## Next integration gate

The next networking tranche should wire the new DNS/rule/attribution foundations into `QuietVpnService` only after a full service-source review and IPv4/IPv6/QUIC tests. Code396 intentionally does not hide an unverified VPN transport rewrite behind a feature label.
