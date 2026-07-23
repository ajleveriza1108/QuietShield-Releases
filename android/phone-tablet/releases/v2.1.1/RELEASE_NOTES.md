# QuietShield 2.1.1 Final Release

## Identity

- Version name: `2.1.1`
- Version code: `225`
- Package: `com.ajleveriza.quietshield`
- Android phones and tablets only
- Permanent signing certificate unchanged

## App Connection Lock

- `Block all user apps` now uses a strict IPv4/IPv6 packet-routing firewall.
- Only apps selected in the active profile can connect.
- Blocked user apps lose DNS, direct-IP, TCP, UDP, QUIC, IPv4, and IPv6 access.
- Newly installed user apps are blocked until explicitly allowed.
- Essential Android/system packages remain available for device stability.
- Normal mode continues to use all-app DNS ad/tracker protection.
- The misleading `App connection issue` popup is removed.

## Midnight and reboot stability

- Midnight resets daily counters only.
- The daily rollover does not restart the VPN or App Connection Lock.
- Always-on protection and the active profile are restored after reboot.
- Temporary Android Keystore read failures do not delete the saved key.
- Startup license verification separates temporary failure from authoritative
  server denial.
- Privacy-safe dated diagnostics record rollover, boot, VPN, recovery, and
  active App Connection Lock state.

## Licensing

The client recognizes the final server-signed key types:

- Admin
- Unique 21-day tester
- Family: two parents and five family members
- Permanent 25-device giveaway
- Permanent regular three-device Premium

## Distribution status

This build package stages the APK, AAB, checksums, release notes, build report,
and an update-manifest draft locally. It does not publish GitHub releases,
repository files, or `update.json`.

## R2 package-validator correction

The Android TV exclusion check now wraps its pipeline result in an explicit
array before reading `Count`. This prevents a PowerShell StrictMode failure
when the correct phone/tablet payload contains zero Android TV files. The
Android final-release payload is unchanged.

## R3 Windows PowerShell 5.1 compatibility repair

Replaced the malformed multiline source-identity Boolean expression with a
fixed identity-key lookup. Package validation now scans every PowerShell script
for leading binary operators, unsafe direct `Count` access, and PowerShell
7-only operators. The Android final-release payload is unchanged.

## R4 permanent PowerShell validator repair

Removed the self-referential string scan that detected its own `??`, `&&`, and
`||` literals. Windows PowerShell 5.1's parser is now authoritative for syntax
and unsupported operators. Runtime-hazard scanning is limited to the build,
installer, and rollback scripts. The Android final-release payload is
unchanged.
