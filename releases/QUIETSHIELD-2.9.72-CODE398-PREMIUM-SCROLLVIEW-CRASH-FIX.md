# QuietShield Android 2.9.72 — Code398

## Critical PremiumActivity ScrollView Crash Fix

### Root cause
Code397 could crash while PremiumActivity resumed because its UI rebuild path
attempted to add another direct child to an existing android.widget.ScrollView.

Android ScrollView permits exactly one direct child. Android therefore threw:

`java.lang.IllegalStateException: ScrollView can host only one direct child`

The crash originated from PremiumActivity during onResume and could immediately
repeat when Android tried to recreate the activity.

### Fixed
- PremiumActivity now clears/replaces the prior ScrollView direct child before
  rebuilding that content.
- The fix is applied only to definite ScrollView receivers in the PremiumActivity
  onResume rebuild path.
- No HONOR-specific runtime logic is used.
- Added a source invariant gate that rejects an unguarded ScrollView.addView in
  the affected resume path.
- Existing Code397 Play-startup isolation remains unchanged.

### Validation gates
- PowerShell 7.6.5 only.
- Source-aware Kotlin patch verification.
- Debug Kotlin compile.
- Full debug unit tests.
- Release lint.
- Signed release APK.
- Signed release AAB.
- APK certificate/signature verification.
- Repository publication only after all Android gates pass.

### Device evidence
The crash was reproduced on HONOR ELN2-W29 / Android 16 / API 36 with
QuietShield 2.9.71 / Code397. Android ApplicationExitInfo classified the process
exit as APP CRASH (EXCEPTION).

### Recommended validation
- HONOR ELN2-W29 Android 16: cold start, Premium screen, background/foreground,
  rotate, leave/re-enter Premium screen.
- Samsung Android 16: same sequence.
- Verify no repeated PremiumActivity recreation/crash loop.