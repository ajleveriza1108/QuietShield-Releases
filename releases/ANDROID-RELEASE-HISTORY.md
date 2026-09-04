# QuietShield Android — Complete Release History

Documentation-only release history for QuietShield Android.

The app keeps only the latest 20 release-note files in the package to reduce size. Older notes remain here.

## 2.9.79 — Code405

**Lean update history, CA detection, and browser navigation**

- QuietShield now keeps only the latest 20 update logs in the app; the complete release history remains available as documentation on GitHub.
- QuietShield verifies its generated protection CA against Android's user-added certificate store when certificate setup resumes.
- Private Browser Back and Forward now follow the active WebView history, so Forward becomes available after navigating back.
- Updated the navigation-policy regression test to match the corrected webpage-history behavior.
- Google Play Automatic protection remains enabled.

## 2.9.77 — Code403

**Premium screen stability**

- Fixed confirmed HONOR Premium screen ScrollView crash.
- Premium ScrollView has exactly one direct root child.
- Removed temporary mediator and build-once workarounds.
- Google Play Automatic protection remains enabled.

## 2.9.75 — Code401

**Premium screen stability**

- Fixed confirmed HONOR Premium screen crash.
- Premium ScrollView now has exactly one direct root child.
- Removed temporary Code400 addView mediator.
- Google Play Automatic protection remains enabled.

## 2.9.74 — Code400

**Premium ScrollView crash repair**

- Fixed confirmed Premium screen ScrollView crash.
- Premium builder addView calls now use a safe ViewGroup mediator.
- ScrollView content is kept under one internal direct child.
- No HONOR-specific runtime branch.

## 2.9.73 — Code399

**Premium screen lifecycle crash fix**

- Fixed repeated PremiumActivity crash on resume.
- Premium UI hierarchy now builds only once per Activity instance.
- Prevents duplicate ScrollView child insertion.
- Cross-device Android lifecycle fix with no HONOR-specific branch.

## 2.9.72 — Code398

**Critical Premium screen crash repair**

- Fixed repeated PremiumActivity crash on Android 16.
- Premium screen rebuild now respects the ScrollView single-direct-child contract.
- Prevents the resume-time crash loop observed on HONOR ELN2-W29.
- The repair is Android-platform based and contains no HONOR-specific runtime branch.

## 2.9.71 — Code397

**Critical Google Play startup isolation**

- App startup no longer performs automatic Google Play update checks.
- Google Play availability no longer gates the QuietShield home screen.
- Automatic update scheduling is removed from MainActivity startup.
- Manual App Updates remains available after QuietShield has opened.
- Google Play Automatic protection must be disabled for the affected Play release.

## 2.9.70 — Code396

**Network Engine Foundation + Inspector v3**

- QuietShield strengthens explainable filtering, compatibility recovery, modern rule parsing, DNS failover foundations, shared-IP attribution safety, and performance regression gates.
- Connection Explorer v3 adds copy, 10-minute compatibility allowances, permanent allow/block actions, and compatibility guidance.
- Temporary allowances can relax only ads, ad measurement, and tracker decisions; threat and Child Safety rules remain non-overridable.
- Adds an immutable domain/wildcard rule engine with rule source, category, action, and priority metadata.
- Adds encrypted-DNS profile and failover foundations for DoH, DoT, and DoQ without changing the active VPN transport until the service integration gate is complete.
- Adds shared-IP attribution logic so one domain is never guessed when several domains recently resolved to the same address.
- Adds performance regression budgets and OEM help guidance without OEM-specific core networking behavior.
- Retains Code395 Android 16 startup hardening and Google Play startup-safety contracts.

## 2.9.69 — Code395

**Cross-device startup crash repair and Android 16 hardening**

- Fixed an Android 16 startup crash caused by QuietShield rebroadcasting the protected BOOT_COMPLETED system action from the app UID.
- Removed the exported SystemStartupReceiver bridge; Android startup events now go directly to QuietShield's private BootReceiver.
- BootReceiver remains android:exported=false, accepting system-origin startup messages while preventing third-party apps from invoking the internal recovery path.
- Added a strict startup-action allowlist for BOOT_COMPLETED, MY_PACKAGE_REPLACED, and USER_UNLOCKED; unrelated actions are ignored before asynchronous work begins.
- Startup behavior is platform-action based with no manufacturer, model, phone, or tablet branching, reducing OEM-specific compatibility risk.
- Added regression tests for reboot, app replacement, user unlock, unknown actions, stable diagnostics labels, and representative phone/tablet profiles.
- Retains Code394 Network Inspector, Code393 fast VPN recovery, App Connection Lock reapply, Google Play-only in-app updates, and existing licensing/security contracts.
- Retains the SYSTEM_EXEMPTED VPN foreground-service repair and bounded startup recovery/maintenance scheduling.

## 2.9.68 — Code394

**Explainable Private Browser Network Inspector foundation**

- Connection Explorer now separates observed, allowed, partly blocked, mixed, and fully blocked website destinations instead of showing only raw request totals.
- Each current-page destination receives an explainable risk label based on first-party or third-party relationship plus QuietShield's existing filter evidence.
- Unknown high-traffic third-party hosts are explicitly kept unclassified unless QuietShield has real ad, tracker, or threat evidence.
- Connection Explorer now records the last allow or block reason for each destination so compatibility decisions are easier to understand.
- Persistent third-party ad and tracker evidence is ranked above ordinary destinations, while known threats receive the highest review priority.
- Private Browser records allowed decisions for explicit website rules, signed allow filters, authentication compatibility, Web Shields mode, protection-off state, and no-rule matches.
- Current-page network observations remain local and page-scoped; they reset on navigation and do not add a background polling service.
- Added pure unit-tested connection-insight policy logic so future system-wide Network Inspector work can share a stable explainability contract.
- Retains Code393 startup recovery, Mobile-first per-site view memory, Google Play-only update action, and the corrected first-run Quick Actions contract.
- Retains Android VPN, licensing, Private Browser login compatibility, Child Safety placement, and existing non-overridable threat and parent-rule behavior.

## 2.9.67 — Code393

**Startup reliability, Private Browser Connection Explorer, and cleaner controls**

- Private Browser opens unsaved websites in Mobile view by default and remembers Mobile or Desktop separately for each website.
- Improved Android startup reliability so protection is requested immediately after boot when automatic startup is enabled, protection was previously on, and VPN permission is already granted.
- Added a system-startup bridge so Android boot, app replacement, and user-unlock broadcasts reliably reach QuietShield while internal recovery actions remain private.
- Private Browser now has its own Connection Explorer for the current page, showing observed first-party and third-party destinations, request counts, blocked counts, and known categories.
- Persistent or pesky ad/tracker destinations are highlighted only after QuietShield has already classified repeated blocked requests as ads, ad measurement, or trackers; high traffic alone is not treated as proof.
- First-run Quick Actions are App Lock, Internet Rules, App Updates, Allow/Block, Compatibility, and Connection Explorer; existing customized Quick Actions remain unchanged.
- App Updates now keeps a single Open Google Play action while still showing the current Google Play update status.
- Child Safety moved out of the duplicated Home/Admin overview and now appears at the top of App protection above App Ad Protection.
- Retains the Code391 Private Browser sign-in/navigation repair and authentication-cookie compatibility.
- Retains license-key sharing, startup release notes, Android 16 VPN stability, and the removal of background-media foreground-service requirements.

## 2.9.66 — Code392

**Private Browser sign-in stability and clean release**

- Promotes the clean Private Browser sign-in navigation repair to QuietShield 2.9.66.
- Retains raw OAuth, SSO, callback, state, nonce, and redirect parameters without QuietShield rewriting them during authentication.
- Retains same-WebView sign-in navigation so target-window login flows do not lose their authentication context.
- Retains Premium and Family license-key copy, paste, and Android sharing support.
- Retains startup What's New, universal Mobile and Desktop website view, and Android 16 VPN stability repairs.
- Private Browser background-media foreground playback remains removed to keep the Google Play foreground-service surface minimal.

## 2.9.65 — Code391

**Private Browser sign-in navigation repair**

- Fixed sign-in buttons that opened briefly and returned to the previous page.
- Preserves authentication callback, state, nonce, redirect, and code-challenge parameters during sign-in.
- Keeps user-clicked sign-in and SSO target-window navigation in one continuous Private Browser WebView.
- Keeps first- and third-party authentication cookies available during the protected sign-in window.
- Keeps threat, child-safety, parent, and imported blocking rules enforced during authentication.
- Retains Premium and Family key sharing, startup What's New, Mobile/Desktop view, and Android 16 VPN stability fixes.

## 2.9.64 — Code390

**Private Browser sign-in compatibility**

- Fixed Private Browser sign-in flows that could be interrupted by browser protection.
- Allows normal first- and third-party authentication cookies during a detected sign-in session.
- Allows genuine user-clicked authentication and SSO popup flows while continuing to block automatic popups.
- Prevents redirect-loop protection and overridable ad/tracker rules from breaking an active sign-in exchange.
- Keeps threat, child-safety, parent, and imported blocking rules enforced during sign-in.
- Retains Premium and Family key copy, paste, and share support plus Google Play purchase restore guidance.

## 2.9.63 — Code389

**Private Browser sign-in reliability**

- Fixed Private Browser sign-in failures by restoring login-compatible first- and third-party cookie handling for normal browser sessions.
- Improved OAuth, SSO, CAPTCHA, callback, token, and session handoffs without weakening Threat, Child Safety, custom, or imported blocking rules.
- Improved login persistence by flushing successful WebView cookie sessions after page loads and before Private Browser is backgrounded.
- Retains manual Premium and Family license key copy, paste, and Android sharing support plus Google Play purchase restore guidance.
- Retains startup What's New, universal Mobile/Desktop website view, per-website view memory, and the Android 16 VPN stability repair.

## 2.9.62 — Code388

**License sharing and purchase restore improvements**

- Added safer copy, paste, and Android Share support for manual Premium and Family license keys.
- Google Play purchases remain account-based: restore the purchase while signed in to the Google account that bought it; Google Play does not create a QuietShield license key.
- The complete manual key stays hidden during normal use and is exposed only when the user explicitly chooses Copy or Share.
- Retains the one-time What's New dialog after app updates, universal Mobile/Desktop website view, and per-website view memory.
- Retains the Android 16 VPN stability repair while keeping the removed background-media foreground-service feature disabled.

## 2.9.61 — Code387

**Startup release notes and Play release continuity**

- Restored the one-time What's New dialog after QuietShield is updated and the main screen opens.
- The startup release note is shown once per installed version and is not repeatedly shown on every launch.
- Retains the universal Mobile and Desktop website view introduced in Code386, including per-website remembered view mode.
- Retains the Android 16 VPN foreground-service crash repair from Code385.
- Uses a new Google Play version code so existing installations have a valid upgrade path to this release.

## 2.9.60 — Code386

**Reliable Mobile and Desktop website view**

- Rebuilt Private Browser Mobile and Desktop view as a universal website rendering mode instead of a site-specific workaround.
- Desktop view now combines a desktop browser identity, desktop User-Agent Client Hints, a 980 CSS-pixel document viewport, and overview-fit scaling.
- Mobile view restores the device browser identity and the website's native responsive mobile viewport on reload.
- Per-website view choices continue to be remembered across pages, subdomains, redirects, tabs, and future visits.
- Retains the Code385 Android 16 VPN foreground-service crash repair, Web Shields, downloads, privacy protections, and memory stewardship.

## 2.9.59 — Code385

**Android 16 VPN startup stability**

- Fixed the VPN foreground-service startup crash affecting Code384 on Android 16.
- Aligned the QuietVpnService runtime foreground-service type with the system-exempted VPN manifest declaration.
- Retained the removal of the media-playback and special-use foreground-service permissions.
- Retained per-website Mobile and Desktop view memory in Private Browser.
- Retained memory stewardship, Web Shields, downloads, tabs, privacy protections, and normal in-browser media playback.

## 2.9.58 — Code384

**Simpler foreground service permissions**

- Private Browser keeps the per-website Mobile and Desktop view behavior introduced in the previous update.
- Removed the Private Browser media-playback foreground service and its media-playback foreground-service permission.
- QuietShield VPN now uses Android’s system-exempted VPN foreground-service category instead of special use.
- Removed the old Private Browser lock-screen background-media preference and related service controls.
- Memory stewardship, Web Shields, downloads, tabs, privacy protections, and normal in-browser media playback are retained.

## 2.9.57 — Code383

**Consistent Website View**

- Mobile and Desktop view now stay consistent across pages on the same website.
- Website view choices are remembered per site, including normal subdomains such as www and mobile hosts.
- Switching tabs, following redirects, and opening links now applies the saved website view before loading.
- Existing Private Browser media, Web Shields, downloads, and memory improvements are retained.

## 2.9.56 — Code382

**More reliable background media and lower memory pressure**

- Improves supported Private Browser audio/video playback while the screen is locked and reduces avoidable memory retention without removing browser features.
- Improves supported Private Browser audio/video continuity when the phone is locked or the screen turns off.
- Adds a short foreground media grace window so Android can transition PB to screen-off playback without starving the WebView renderer.
- Keeps the CPU wake lock only for the transition window or real active playback, then releases it automatically.
- Clears recomputable Private Browser caches and large session references when PB is destroyed or Android reports memory pressure.
- Preserves Web Shields, downloads, tabs, media controls, privacy protections and existing browser features.

## 2.9.55 — Code381

**Private Browser media, stronger shields and faster downloads**

- Improves Private Browser media handling, settings readability, browsing protections and supported direct-file downloads.
- Improves Private Browser media handling and supported lock-screen media controls.
- Improves Private Browser Settings text wrapping so longer options remain fully readable.
- Strengthens general Private Browser ad, tracker, popup, redirect and nuisance filtering.
- Improves supported direct-file downloads with safe multipart range downloading and automatic fallback.
- Includes Android compatibility, security, stability and performance improvements.

## 2.9.54 — Code380

**Private Browser media, stricter Web Shields and faster downloads**

- Improves one-at-a-time media playback, supported-site lock-screen controls, general Web Shields, settings readability and direct-file download speed.
- Keeps the screen awake only while the active Private Browser video is playing.
- Supports one active audio or video session with lock-screen Play/Pause, Previous, Next, Stop and Loop controls on compatible websites.
- Supported website media can continue while the phone is locked when Background media is enabled.
- Pauses competing Private Browser media so only one audio/video item is active at a time.
- Improves Private Browser Settings text wrapping so longer options remain fully readable.
- Strengthens general Private Browser ad, tracker, popup, redirect and nuisance filtering without adding service-specific ad bypasses.
- Keeps secure Private Browser downloads and adds bounded multipart HTTP range downloads when a server explicitly supports them, with automatic fallback to the proven single-stream/resume path.

## 2.9.53 — Code379

**QuietShield reliability, Private Browser, updates, and family improvements**

- Green update attention is back: When Google Play has a newer QuietShield build, Settings keeps its green outline, soft green glow, and update attention until the newer build is actually installed. Google Play now owns the in-app update flow.
- Stricter, more resilient Private Browser: Private Browser strengthens Strict Web Shields, covers Service Worker requests, and can recover affected tabs after repeated renderer hangs or renderer termination without storing browsing history in reliability diagnostics.
- Protection recovery is easier to diagnose: QuietShield improves VPN restart backoff, default-network handoffs, IPv4/IPv6 DNS diagnostics, VPN-revocation reporting, and protection health evidence so unexpected interruptions are less likely to be silent.
- Administrator child controls are easier to find: Administrator Settings now exposes Parent Command Center, Add managed child, and Linked child devices directly. Child health shows the reported QuietShield version and the last verified Parent policy remains enforced locally during temporary sync outages.
- Performance and maintainability foundation: A conservative baseline profile covers important startup, protection, Private Browser, update, Premium, and family paths, while privacy-safe diagnostics include Private Browser reliability counters.
- What's New remains a once-per-installed-version popup and Update log remains available from Settings.
- Google Play Billing, Premium, Family, Restore, the 7-day public trial, and Code373 phone fullscreen smart rotation remain preserved.
- YouTube-specific suppression remains disabled in the Google Play distribution; Private Browser improvements use general browser-owned filtering and reliability layers.
- Debug-only LeakCanary and performance metrics instrumentation remain excluded from release behavior.
- Large Activity cleanup remains incremental rather than a risky all-at-once rewrite.
- QuietShield 2.9.53 brings the complete Code375-Code379 reliability cycle into one customer release.

## 2.9.52 — Code378

**Parent and child reliability and clearer Admin controls**

- Administrator child setup is explicit: Administrator Settings now exposes Parent Command Center, Add managed child, and Linked child devices directly instead of requiring the user to know a hidden family path.
- Child health shows more useful detail: Family Protection includes the child’s reported QuietShield version alongside presence, protection, policy delivery, management level, and last contact.
- Last verified policy survives outages: When Parent policy sync is temporarily unavailable, the Managed Child keeps enforcing its last verified local policy and says so clearly instead of implying protection disappeared.
- Admin Managed Child QR continues to use isolated Admin Sandbox Family inventory.
- The private Administrator credential is never placed in child enrollment QR data.
- Missing child heartbeats remain availability warnings and do not claim an uninstall Android cannot prove.
- QuietShield 2.9.52 makes Parent/Child behavior easier to discover and safer during temporary connectivity/server outages.

## 2.9.51 — Code377

**VPN and network reliability hardening**

- Bounded VPN recovery: Repeated unexpected VPN-service destruction now backs off progressively instead of creating a tight restart loop. Backoff resets only after protection remains healthy for five minutes.
- Cleaner Wi‑Fi/mobile handoff: Duplicate default-network callbacks no longer clear DNS state repeatedly. QuietShield coalesces network changes and records whether the underlying network exposes IPv4 and/or IPv6 DNS.
- VPN revocation is clearer: When Android revokes QuietShield VPN ownership, diagnostics distinguish ordinary consent loss from the case where another VPN transport is visible, without claiming more than Android can prove.
- IPv4 and IPv6 tunnel/DNS routes remain enabled.
- Existing 15-minute Protection Supervisor stays independent of tight restart loops.
- Saved App Connection Lock and protection settings remain intact after VPN revocation.
- QuietShield 2.9.51 focuses on predictable recovery, network handoff, and useful technical evidence.

## 2.9.50 — Code376

**Private Browser reliability and stricter request coverage**

- Service Worker requests are covered: Private Browser now applies a bounded Web Shield client to Service Worker network requests, closing a request path that ordinary WebView interception does not own.
- WebView renderer recovery is stronger: Renderer crashes and Android renderer kills are recorded without browsing history. Repeated renderer hangs can trigger a bounded renderer restart instead of taking down the whole app.
- Reliability diagnostics stay private: QuietShield records only technical renderer and Service Worker counters—not URLs, search terms, page titles, cookies, accounts, or browsing history.
- Preserves Android WebView Safe Browsing.
- Preserves Google Play restrictions on YouTube-specific suppression.
- A single temporary renderer stall never triggers automatic termination.
- QuietShield 2.9.50 makes Private Browser stricter while keeping compatibility fallbacks and privacy-safe diagnostics.

## 2.9.49 — Code375

**Google Play update attention restored**

- Green Settings glow is back: When Google Play reports a newer QuietShield build, Settings keeps a green soft glow, green outline, and green icon attention until the newer build is actually installed.
- Google Play is authoritative: QuietShield now checks Google Play directly for production update availability instead of relying on the retired direct APK update channel.
- What’s New stays separate: Update available and What’s New are separate states: the green update attention belongs to a newer build, while What’s New appears once after a genuine upgrade.
- Adds Play Core in-app update status and Google Play-owned flexible/immediate update flows.
- Normal updates no longer hijack app launch; Settings remains visibly highlighted instead.
- High-priority Play updates may use the immediate flow only when Google Play permits it.
- QuietShield 2.9.49 restores persistent update attention without bringing back self-downloaded APK updates.

## 2.9.48 — Code374

**Protection Reliability and stricter Private Browser shields**

- Protection recovery: QuietShield now records more Android/OEM shutdown evidence and adds an independent periodic supervisor that can request recovery when protection is enabled but the VPN service is missing.
- Private Browser Strict protection: New websites use the stricter Private Browser shield profile by default, with conservative third-party ad and tracking-script detection while preserving explicit per-site choices.
- What’s New is back: A What’s New popup is shown once after every genuine app update and remains available from the Update log.
- Adds cold-start process-exit diagnostics for hard/OEM kills.
- Logs task removal, unexpected VPN destruction, and restart-alarm status without browsing history.
- Keeps Google Play distribution boundaries and customer purchase behavior unchanged.
- QuietShield 2.9.48 focuses on staying protected, explaining interruptions, and keeping Private Browser cleaner.

## 2.9.47 — Code373

**Fullscreen video and purchase experience improvements**

- Fullscreen smart rotation: Fullscreen video on phones can use sensor landscape even when Android Auto rotate is off, while tablets and multi-window stay adaptive.
- Clearer purchase information: Premium and Family screens now explain device limits, one-time purchase status, and Google Play restore more clearly.
- Premium: permanent access for up to 3 active Android devices.
- Family: permanent access for up to 5 active Android devices.
- License-server readiness recovery was strengthened.
- Reliability and purchase UX improvements.

## 2.9.46 — Code372

**Production cleanup and standard 7-day trial**

- Standard public trial: The normal 7-day Premium trial is restored for public customers.
- Production cleanup: Retired beta-tester wording was removed and Android 16 system-bar compatibility was improved.
- Customer-facing beta tester controls are retired.
- The 7-day Premium trial remains available.
- Google Play remains the Android update source.
- Production-ready cleanup for QuietShield on Google Play.

## 2.9.45 — Code371

**Google Play purchases and license restoration**

- Google Play purchasing: QuietShield Premium and Family one-time purchases can be completed and restored through Google Play.
- Server-verified entitlement: Google Play purchases are verified by the QuietShield license service before permanent entitlement is granted.
- Premium supports up to 3 active devices.
- Family supports up to 5 active devices.
- Restore purchase remains available through Google Play.
- One-time purchase. No subscription.

## 2.9.44 — Code370

**Backup compatibility and Google Play migration**

- Restores portable QuietShield backup files selected as .bin, .qs, or JSON without relying on the provider MIME type.
- Quick Actions selection and saved order are included in portable backup and restored with the rest of the supported settings.
- Google Play remains the only customer update source after Code368.
- Code370 keeps the permanent QuietShield signing identity and Play-only update channel.

## 2.9.43 — Code369

**Google Play transition, browser view repair, and family reliability**

- Google Play update channel: Starting with QuietShield 2.9.43, customer app updates are handled by Google Play. The final GitHub updater remains Code368 only. Private Browser Mobile/Desktop view switching now restores both the correct user agent and viewport.
- Existing installations continue in place: QuietShield keeps the same Android package identity and per-device Parent/Managed Child role model. Parent Command Center remains Parent/Admin-only, while Managed Child routing, policy sync, and website requests remain enforced.
- Server updater permanently closed: QuietShield 2.9.42 / Code368 remains the final server/GitHub updater release. Game Performance Mode can reduce optional QuietShield allowed-request logging, but never speeds up, skips, clicks, or modifies ads in other apps.
- Google Play is the Android customer update source for Code369 and later.

## 2.9.42 — Code368

**Important update: QuietShield is moving to Google Play**

- Final direct/server update: QuietShield 2.9.42 is the final app update delivered through the existing QuietShield server/GitHub update channel.
- Future updates move to Google Play: Starting with QuietShield 2.9.43, app updates will be delivered through Google Play. Keep QuietShield installed and use its Google Play listing for future updates when 2.9.43 becomes available.
- Google Play preparation: Code368 adds the distribution boundary needed for the Google Play transition while preserving the current working QuietShield protection, licensing, Private Browser, and direct-release source lineage.
- 2.9.42 / Code368 is the final direct/server-delivered QuietShield Android update.
- 2.9.43 / Code369 and later customer updates move to Google Play.
- The existing GitHub updater implementation remains in source for now; the server feed simply ends at Code368.
- The Play-prepared build includes Google Play Billing Library 9.1.0.
- The Play-prepared build excludes QuietShield-specific YouTube suppression while retaining ordinary security, child-safety, and privacy protections.
- Important: after installing 2.9.42, future QuietShield Android app updates will come from Google Play beginning with 2.9.43.

## 2.9.41 — Code367

**Safer second-tab behavior in Private Browser**

- Second tab is explicit-user only: Websites, ad redirects and popup scripts can no longer consume the empty second Private Browser tab. Passive webpage navigation cannot use it; the slot remains for explicit user-driven browser actions such as the + button or Open link in a new tab.
- Popup navigation stays contained: Allowed user-gesture target-window navigation is resolved into the current tab and continues through QuietShield navigation protections rather than being promoted into another tab.
- Code366 link menu retained: The visible long-press actions for new tab, Incognito, Share, Copy link address and Copy text remain available.
- Automatic cross-site second-tab opening removed.
- Legacy cross-site new-tab preference is cleared when Settings is applied.
- Code366 link-action menu and Code365 browsing-data/history/tab/settings behavior are retained.

## 2.9.40 — Code366

**Private Browser link long-press menu repair**

- QuietShield repairs the Private Browser link context menu so the requested actions are visibly rendered instead of showing only the link preview.
- Visible link actions: The long-press dialog now uses explicit clickable rows, so the five requested commands are always visible when applicable.
- Second-tab rule retained: Open link in a new tab appears only while the second Private Browser tab is available.
- Long-pressing a web link now renders dedicated visible action rows for Open link in a new tab when the second tab is free, Open link in incognito, Share link, Copy link address, and Copy text.
- The repair no longer depends on the ModernDialogUi list-item adapter path that could display the link preview while omitting the action choices.
- Each link action is presented as a full-width themed row with the active QuietShield surface, outline, readable text, and a minimum touch target.
- The existing Code365 link-target resolution remains intact, including requestFocusNodeHref fallback handling for normal anchors and image anchors.
- Code365 browsing-data ranges, direct history rows with trash deletion, persistent tabs, responsive Settings, and all retained Code364/Code363 protections remain unchanged.
- Code366 is a guarded Direct GitHub release. PRIVATE source publishes first, public APK/checksum second, and signed updater metadata last after all Android and signer gates pass.

## 2.9.39 — Code365

**Private Browser history controls, link actions and responsive settings**

- QuietShield adds time-range browsing-data clearing, cleaner history controls, persistent tabs, a complete link long-press menu, and responsive Private Browser Settings text.
- Clear recent browsing data: Choose 4, 12, or 24 hours, or All the time, while keeping WebView-only all-time limitations explicit instead of silently over-deleting.
- Complete link long-press actions: Open in a free second tab, switch safely to Incognito, share, copy the address, or copy the visible link text.
- Persistent tabs and readable Settings: Tabs stay visible during normal browsing and long Settings labels wrap within the screen without being hidden behind the action bar.
- Clear browsing data now offers 4 hours ago, 12 hours ago, 24 hours ago, and All the time ranges. QuietShield history and site-scoped cookies/storage follow the selected recent range; Android WebView cache and saved form data remain clearly labeled as all-time-only because the platform does not expose safe time-scoped deletion for them.
- Private Browser history cards open directly when tapped. The redundant Open button is removed and each entry keeps a compact trash-icon delete action.
- The Private Browser tab strip remains visible during normal browsing instead of being accidentally hidden by the Tabs controls. Deliberate page fullscreen remains immersive.
- Long-pressing a web link now offers Open link in a new tab when the second tab is free, Open link in incognito, Share link, Copy link address, and Copy text.
- Private Browser Settings uses dedicated wrapping toggle rows and bottom safe-area padding so long labels remain readable and the final options can scroll above Cancel and Apply.
- Code364 structured update notes, theme-consistent Incognito/View controls, Code363 Connection Explorer completeness, Incognito watermark, and Android 16 VPN recovery are retained.
- Code365 is a guarded Direct GitHub release. PRIVATE source publishes first, public APK/checksum second, and signed updater metadata last after exact Git-blob and RSA verification.

## 2.9.38 — Code364

**Clean update notes and theme-consistent Private Browser controls**

- QuietShield now renders structured What's New cards correctly and keeps the Incognito and View controls visually consistent with the rest of the Private Browser navigation in every theme.
- Readable What's New cards: Release highlights now display a clean title and description instead of the raw JSON object that appeared in Code363.
- Consistent Private Browser controls: Incognito and View now use the same themed surface and border styling as Home, Bookmarks, History and Settings.
- Existing Code363 protections retained: Connection Explorer completeness, system-app safety, the Incognito Speed Dial watermark and bounded Android 16 VPN recovery remain intact.
- What's New and Update log now render release highlight titles and descriptions as proper UI content instead of exposing raw JSON objects.
- Release-note parsing now uses the structured bundled highlight model directly, with a safe legacy fallback for older plain-text release entries.
- Incognito and View no longer draw their own bright outer border; both use the same theme surface and outline tokens as Home, Bookmarks, History and Settings.
- Incognito may still accent its glyph while active, but its container remains theme-consistent.
- All Code363 Connection Explorer, Incognito watermark and Android 16 VPN recovery behavior is retained.
- Code364 is a guarded Direct GitHub release. PRIVATE source publishes first, public APK/checksum second, and updater metadata last after exact signer verification.

## 2.9.37 — Code363

**Complete Connection Explorer, Incognito cue and Android 16 VPN recovery**

- QuietShield keeps user and system apps available in Connection Explorer, adds a large Incognito watermark behind Speed Dial, and strengthens bounded Android 16 VPN-manager recovery for QS-P02-B6E2465E while preserving the Code362 R2 Private Browser refinements.
- All installed apps in Connection Explorer: User and system packages are loaded together, and apps do not need existing destination history to appear in the main inventory.
- Stronger Incognito state cue: A large, subtle Incognito watermark sits behind Speed Dial content whenever the isolated Incognito profile is active.
- System-app safety preserved: System packages are visible for inspection, while existing system-app warnings and supported network-policy boundaries remain intact.
- Android 16 VPN recovery strengthened: QS-P02-B6E2465E now receives additional bounded cooldown retries for the exact Android VPN-manager establish failure shape, while persistent failures still stop and remain reportable.
- Connection Explorer now loads the complete user and system app catalog instead of making system-app visibility optional.
- Installed apps remain visible in Connection Explorer even before QuietShield has recorded a destination for them, so they can be inspected or selected for observation immediately.
- The former System apps show/hide control is now a safety-information control; existing system-app warnings and supported network-policy safeguards remain unchanged.
- When Incognito is active, Speed Dial displays a large low-opacity Incognito icon in the background without intercepting taps or accessibility focus.
- Code362 R2 Private Browser behavior is retained: framed Incognito button, persistent View button, per-site Mobile/Desktop memory, narrow-screen Settings wrapping, edition-gated Child Safety wording and pencil-mode close behavior.
- Android 16 VPN-manager recovery now gives the exact IVpnManager.establishVpn / VpnService.Builder.establish IllegalStateException a longer but bounded cooldown window before final escalation; unrelated IllegalStateException failures remain reportable.
- The separate Past 2 Months monthly history/report update is intentionally not included in Code363.
- Code363 R1.2 is a guarded repository-publishing release: all Android gates run first, PRIVATE source publishes first, public APK/checksum second, and signed updater metadata last. The deferred Past 2 Months report change remains excluded.

## 2.9.36 — Code362

**Private Browser view memory and safety gating**

- QuietShield refines Private Browser navigation with a persistent website-view toggle, cleaner settings wrapping, safer Child Safety visibility, and faster Speed Dial editing.
- Per-site website view memory: QuietShield can now remember Mobile or Desktop view for the current website and restore that choice the next time the user visits it.
- Cleaner Private Browser chrome: Incognito receives a matching framed icon, Settings text wraps correctly, and the six-button bottom bar stays consistent on phones and tablets.
- Safer family visibility: Child Safety wording remains visible only for Administrator and Parent-capable editions, keeping regular-user surfaces cleaner.
- Private Browser bottom navigation now keeps Home, Bookmarks, History, Incognito, View and Settings in one stable order.
- The new View button toggles Mobile and Desktop website view, and remembers the selected view for the current website.
- Incognito now uses the same framed visual treatment as the other bottom-nav icons.
- Private Browser settings wrap long option text to stay readable on narrow screens.
- Child Safety wording stays hidden from Private Browser surfaces unless the edition resolves to Administrator or Parent-capable serials.
- Speed Dial pencil mode closes cleanly as soon as the user taps a destination or empty area.
- QuietShield keeps guarded release publication, local-only safety analysis and source-aware recovery in place.

## 2.9.35 — Code361

**Private Browser and Device Safety refinement**

- A focused usability and safety release that preserves QuietShield's existing protection engine.
- Private Browser now uses the approved adaptive phone/tablet five-button navigation: Home, Bookmarks, History, Incognito, and Settings.
- Speed Dial uses a pencil-controlled arrangement mode; normal long-press edits nickname and URL while preserving folder/order placement.
- Device Safety Scan provides a local summary and per-app review using Aggressive App Watch signals without claiming perfect malware detection.
- What's New and Update log return to the professional card-based presentation with CURRENT markers and collapsed technical details.
- Tabs and Downloads remain available from the browser menu; Settings is a direct bottom-navigation destination.
- No new dangerous permissions, remote scanner, ADB install, or Android/Play Protect bypass is introduced.
- Release-signing material, AABs, and R8 mapping remain private.

## 2.9.34 — Code360

**Protection control consistency**

- When QuietShield is paused, tapping the orange protection control now turns protection back on instead of opening another ten-minute turn-off choice.
- The What's New Update log is restored as a persistent bundled history: Code360 and earlier bundled release notes remain reopenable and no longer render as an empty page.
- The main protection control now uses one shared state policy for both its action and accessibility label, preventing PAUSED from being mistaken for fully ON.
- Protected remains green, paused remains orange, and protection off remains warning red.
- Code359 Private Browser controls, dashboard return-state repair, Connection Intelligence, FileSafety, anti-rollback security, and signed-update protections are retained.

## 2.9.33 — Code359

**Private Browser control + Connection Intelligence + dashboard state repair**

- Private Browser Data Saver toggle reduces page data by leaving network images unloaded until Data Saver is turned off.
- Long-press a webpage link to open it in the empty second tab; direct cross-domain/subdomain clicks also use the empty second tab by default.
- Speed Dial items inside folders again expose Edit and Remove controls.
- Custom website rules are directly reachable from Private Browser Settings, Web Shields, and Search Engine settings.
- Connection Explorer now shows conservative purpose and frequency intelligence without inventing labels for unknown destinations.
- Returning from Private Browser now preserves the exact Home, Protection, Activity, or Settings section that launched it, so the Home navigation button and selected-section glow stay correct.
- Home no longer shows the redundant Protection health entry.
- Protection state signaling is explicit: protected is green, paused is orange, and protection off is warning red.

## 2.9.32 — Code358

**Quality, Performance & Visual QA Foundation**

- Adds developer-side visual regression, debug memory/jank diagnostics, static build-health checks, and permanent AI/release rules without changing QuietShield's production protection model.
- Safer UI changes: Roborazzi and Robolectric foundations can record and verify important QuietShield screens on phone and tablet layouts before future UI releases.
- Debug performance visibility: Debug builds can surface memory leaks and janky frames during manual testing while release builds stay free of continuous QA instrumentation.
- Build health checks: Detekt report mode plus dependency, insecure-repository, dynamic-version, and release-artifact checks make quality drift easier to catch.
- Permanent engineering guardrails: AGENTS.md and QuietShield-specific AI skills preserve release ordering, signer identity, security boundaries, UI readability, and low-resource requirements.
- Visual QA remains opt-in in Code358 so the first baseline can be recorded on the authoritative Windows development environment before screenshot verification becomes a mandatory release gate.
- A documented Macrobenchmark and Baseline Profile plan defines the exact user journeys to measure before production optimization.
- Release builds do not include LeakCanary or JankStats instrumentation.
- Code355-357 signed-update/runtime integrity, Connection Explorer backup/restore, FileSafety, permanent APK signer, and no-new-MITM boundaries remain unchanged.
- Code358 strengthens how QuietShield is tested and maintained so future feature releases can move faster without sacrificing stability.

## 2.9.31 — Code357

**Premium UX & Density Consolidation**

- Simplifies QuietShield's busiest screens with list-first layouts, progressive disclosure, searchable rules, compact Quick Access, and a clearer Protection Health view.
- Protection Activity is list-first: Long guidance moves behind About, daily totals are compact, result cards are tighter, and the activity list gets more of the screen.
- Web Shields is easier to scan: Long checkbox labels wrap instead of cropping, common controls stay up front, and technical/aggressive controls move behind an Advanced section.
- Internet Rules is searchable: Examples and long guidance move behind Help, while saved rules can be searched and filtered by All, Enabled, or Disabled.
- Details only when you need them: How QuietShield Works uses compact summaries with Read details, Expand all, and Collapse all controls for easier reading.
- Quick Access uses thinner selected rows and a compact Add shortcut chooser instead of a long inline Available section.
- Connection Explorer links directly to Protection Activity, including an app-filtered activity view from app tools.
- Home adds a Protection health entry and Protection Intelligence becomes a compact health dashboard.
- Code355/356 runtime security, Connection Explorer backup/restore, permanent APK signer, package identity, and no-new-MITM boundary remain protected.
- Code357 is a UX consolidation release: simple by default, detailed on demand.

## 2.9.30 — Code356

**Compact UI & Readability Repair**

- Gives Protection Activity more list space, makes Web Shields fully scrollable, compacts Quick Access rows, and improves How QuietShield Works readability.
- More room for Protection Activity: Shorter guidance, tighter summary spacing, compact result cards, and side-by-side activity controls leave substantially more vertical space for recent app/network decisions.
- Web Shields no longer crops text: The Web Shields dialog content now scrolls independently above the fixed dialog actions so filter-list, aggressive-activity, cookie, and website-control text remains reachable.
- Thinner Quick Access rows: Internet Rules, App updates, Allowlist and Blocklist, Compatibility Exclusions, Connection Explorer, and other shortcuts use one compact title/control row instead of tall stacked cards.
- A more readable QuietShield guide: How QuietShield Works adds breathing room between labels, headings, paragraphs, and long explanations, with multi-paragraph sections for dense topics.
- Quick Access reorder/remove controls keep compact dedicated touch targets while using far less vertical space.
- Protection Activity keeps the same filters, search, decision explanations, repeated-request toggle, and clear-history behavior.
- No filtering, VPN, licensing, backup/restore, updater-security, package-safety, or HTTPS-MITM boundary is weakened by this UI release.
- Code356 is a presentation and readability release on top of the Code355 APK/runtime security and Connection Explorer backup foundation.

## 2.9.29 — Code355

**APK & Runtime Security Hardening**

- Signed update manifests, runtime release-integrity enforcement, explicit backup exclusions, supply-chain/release gates, and portable Connection Explorer backup/restore.
- Signed update trust: Future direct updates require a detached signature from a separate QuietShield update-manifest key plus APK SHA-256, signer identity, and anti-rollback checks.
- Connection Explorer backup: Portable .qs backups now include observed-app selections and bounded Connection Explorer destination evidence while excluding temporary learning timers and diagnostic runtime state.
- Runtime integrity: Sensitive update and restore operations verify the installed release signing identity; release WebView debugging is forced off.
- Backup and release hardening: Android cloud/device-transfer backups are explicitly excluded, cleartext remains disabled, and release packaging adds manifest/dependency/secret-leakage security gates.
- Connection Explorer portable evidence is restored separately from Recent Activity so historical traffic is not misrepresented as new-device traffic.
- License/device identity, parent/admin credentials, tokens, cookies, sessions, temporary learning timers, and signing secrets remain excluded from portable backup.
- The update-manifest private key remains outside source/public artifacts; only its certificate is embedded in the APK.
- Security hardening keeps QuietShield's existing no-package-disable/hide/suspend and DNS-focused/no-new-HTTPS-MITM boundaries.

## 2.9.28 — Code354

**Compact Connection Explorer UI**

- Connection Explorer gives the destination list most of the screen again, and release-note cards no longer render internal semantic icon labels as jumbled text.
- Connection Explorer: Moves the long explanation behind About, compresses destination filters, and replaces the stack of large actions with Profile, Learning, and Tools so the domain/subdomain list receives most of the screen.
- Update Log: Stops internal semantic icon labels such as shield, connection, activity, and filter from rendering as wrapped visible text; cards use a compact accent rail and full-width readable content instead.
- Profile remains directly accessible; Refresh, Undo last manual rule, and About are grouped under Tools.
- Blocked/Allowed/Unknown/Direct-IP current-state filters and stable list-position restoration are retained.
- Protection Intelligence behavior, diagnostics, filter-source intelligence, DNS-focused visibility boundaries, and no-HTTPS-MITM policy are unchanged.
- This is a UI-density and release-note rendering repair; protection decisions and packet-engine boundaries are unchanged.

## 2.9.27 — Code353

**Protection Intelligence**

- QuietShield now connects app destinations, recent activity, filter-source health, and per-app diagnostics into one evidence-driven protection workflow.
- Protection Intelligence: A new dashboard summarizes active protection modules and opens the evidence behind Connection Explorer, filter sources, activity, rules, DNS health, and threat protection.
- Connection Explorer: App details add Unknown and Direct IP evidence filters, filter-source provenance, a consolidated per-app protection profile, and a local before/after ad and tracker diagnostic session.
- Protection activity: Recent activity now combines allowed and blocked decisions, supports search and Unknown/Direct-IP filters, and collapses repeated identical attempts unless raw requests are requested.
- Protection filter sources: Source settings now show health, update/revision status, compatibility, estimated overlap, and estimated unique contribution while runtime deduplication stays exact.
- Diagnostic sessions use the existing local EventLog and selected-app observation; they do not add another packet scanner.
- Current filter-source provenance is resolved from enabled compiled domain lists and is clearly distinguished from the historical stored decision source.
- Standard QuietShield protection remains DNS-focused and does not claim visibility into hostname-opaque direct-IP or private encrypted-DNS traffic.
- HTTPS MITM is not added by Code353; existing optional secure-website inspection remains separate.
- Connection Explorer and Protection Intelligence are evidence tools. Blocking unknown endpoints can break app functions, especially shared/CDN or system destinations.

## 2.9.26 — Code352

**Connection Explorer filters + cleaner app discovery + stable list position**

- • Filter each app by All, Blocked, or Allowed destinations.
• Counts now reflect the same current state shown in the list.
• The main Explorer shows only apps that already have captured destinations.
• Rule changes no longer jump the destination list back to the top.
- Connection Explorer: All / Blocked / Allowed filters now use each destination’s current effective QuietShield state, so the visible Allowed count always corresponds to entries the Allowed filter can actually show.
- Connection Explorer: The main app list now contains only installed user/system apps with captured exactly-attributed destinations; Observed apps remains available to select a new app before its first destination appears.
- Connection Explorer: Blocking, allowing, removing a rule, saving a Link Guard exception, undoing, refreshing, or toggling Learning Mode preserves the user’s list position instead of returning to the top.
- Historical allowedCount/blockedCount totals are no longer used as current-state destination counters. A saved current BLOCK/ALLOW rule takes precedence, otherwise the latest observed decision is used.
- Filter buttons display current counts as All (n), Blocked (n), and Allowed (n); the active filter is visibly marked.
- App discovery scans the existing bounded EventLog once for exactly-attributed packages with nonblank destinations and intersects that set with the installed-app catalog.
- The Observed apps picker intentionally remains broader than the main Explorer list so opt-in observation can start before any hostname has been captured.
- Viewport restoration anchors to the first visible domain and its top offset; if that domain leaves the active filter after a rule change, the nearest previous position is retained.
- How QuietShield Works is updated for the Code352 Connection Explorer behavior.
- A more trustworthy Connection Explorer: current-state counts, useful filters, relevant apps only, and no jump-to-top after rule changes.

## 2.9.25 — Code351

**Activity drill-downs + UI polish + complete selected-app Explorer inventory**

- • Data Savings date/range rows now open real local drill-downs.
• Update cards consolidate repeated items by category.
• Mobile Data Watch background alerts require an active cellular route.
• Selected Connection Explorer apps retain all attributable allowed and blocked hostnames.
- Improvement: Data Savings Last 7 days, Last 30 days, month, and date rows now open useful local totals and daily breakdowns instead of behaving like dead buttons.
- Improvement: Settings update attention remains QuietShield green even when Settings is selected; the normal blue selected styling is suppressed until the update-attention state clears.
- Improvement: The tablet protection logo is clipped to the same rounded-square geometry as the phone treatment and inset from its green protection border.
- Improvement: Edit Quick Settings uses thinner Move Up, Move Down, and Remove vector icons instead of Android's heavy legacy stock glyphs.
- App Connection Lock: Mobile Data Watch background scans and notifications are gated by the current active cellular route, so Wi-Fi cannot trigger the Watch.
- App Connection Lock: Connection Explorer selected-app observation now retains every exactly attributable allowed or blocked hostname/subdomain QuietShield sees, while preserving the no-HTTPS-MITM boundary.
- Data Savings range, month, and day chevrons now open local details. The report remains totals-only and does not add website, DNS, or browsing history.
- ReleaseNotesCenter and the post-update What's New renderer consolidate repeated highlight titles into one category card, preserving all bodies as bullet items.
- Verified Settings update attention overrides normal blue selection styling until the attention state clears.
- The Home protection logo image is clipped to rounded-square geometry on phone and tablet and retains internal inset from its protection border.
- Edit Quick Settings uses QuietShield-owned thin-stroke vector controls for Move Up, Move Down, and Remove.
- Mobile Data Watch scheduled/background scans require MobileDataRoute.isActive() to report an active cellular transport before scanning or notifying; manual historical cellular review remains available.
- Connection Explorer selected-app observation records ordinary allowed hostnames as well as blocked/warning destinations through the existing exactly-attributed EventLog path.
- Connection Explorer status shows observed, blocked, and allowed destination counts and explicitly documents the direct-IP/encrypted-name visibility boundary.
- How QuietShield Works is updated for the new Data Savings, update-card grouping, cellular-only Watch trigger, and selected-app destination inventory behavior.
- Cleaner drill-downs, consistent attention styling, cellular-only Watch alerts, and more complete selected-app destination visibility without weakening QuietShield's privacy boundaries.

## 2.9.24 — Code350

**Connection Explorer usability + per-app block alerts**

- • Connection Explorer keeps the app list as the main screen area.
• Search stays usable when the digital keyboard opens.
• System apps can be shown with a safety warning.
• Selected observed apps can notify when QuietShield blocks traffic.
- Connection Explorer replaces its long always-visible explanation with compact controls and an About Explorer dialog so the app list gets most of the screen.
- The app picker explicitly uses resize/IME-safe behavior and keeps Search above the weighted app list so the digital keyboard reduces the list instead of covering the search field.
- Observation, block/review alerts, observed-app selection, and the System apps toggle are arranged in compact two-column control rows.
- System apps remain hidden by default. Showing them requires a warning that network blocks can affect calls, notifications, sign-in, sync, updates, the launcher, or other device functions; QuietShield still never disables, hides, suspends, or removes packages.
- Hidden system-app observation selections are preserved when the System apps filter is turned off, avoiding accidental loss of existing scoped choices.
- When Connection Explorer observation and alerts are both enabled, actual blocked traffic from selected apps can generate a private notification that opens the app and destination in Connection Explorer.
- Block alerts are rate-limited per app so repeated tracker/ad requests cannot flood the notification shade. Protection and blocking continue even when Explorer observation or alerts are off.
- How QuietShield Works now explains the compact Explorer layout, system-app toggle, selected-app block/review alerts, rate limiting, and the separation between optional observation and configured protection.
- More app-list space, safer system-app visibility, and useful selected-app block alerts without turning Connection Explorer into an all-app recorder.

## 2.9.23 — Code349

**Private Browser Shield + Internet Rules scalability**

- • Web Shields stays visible on every Private Browser page.
• Web Shields highlights repeated classified ad/tracker activity.
• Internet Rules now scroll reliably and support 200 non-redundant rules.
• Quick Actions use unique function-matched icons.
- The Web Shields icon remains visible and usable on Private Browser Home and on every webpage instead of disappearing when web content opens.
- Private Browser Web Shields locally identifies aggressive activity only after a destination has already been classified as an ad, ad-measurement endpoint, or tracker and crosses a repeated-block threshold. Unknown busy domains are not relabeled as trackers merely because they make many requests.
- The Web Shields panel shows the most aggressive blocked ad/tracker destinations and their local blocked-request counts for the current page. The page-local activity resets on navigation and does not create an all-history traffic recorder.
- Internet Rules uses one ListView scrolling surface instead of a ListView nested inside a ScrollView, so long collections remain reachable.
- Internet Rules supports up to 200 effective rules. Semantically equivalent rules are consolidated and the newest equivalent policy replaces the older duplicate rather than consuming another slot.
- Opening Internet Rules compacts pre-existing redundant rules without weakening distinct actions, app scopes, schedules, networks, or targets.
- Connection Explorer has its own unique Quick Action icon, Private Browser uses its browser/globe icon, and every simultaneously selectable Quick Action resolves to a distinct function-matched semantic icon.
- How QuietShield Works is updated for Link Guard, Sensitive Content, Strict App Shield, opt-in Connection Explorer, always-available Private Browser Web Shields, aggressive ad/tracker review, and the 200-rule non-redundant Internet Rules limit.
- Web Shields stays available while browsing, Internet Rules scales cleanly, and advanced visibility remains local and conservative.

## 2.9.22 — Code348

**Connection Explorer opt-in observation and Quick Access**

- • Connection Explorer observation and its review notifications are now opt-in.
• Select only the apps you want Connection Explorer to watch.
• Destination action pop-ups close after a choice and verified rule state is shown.
• Connection Explorer is available in Protection and customizable Quick Access.
- Connection Explorer Observation defaults off. Turning it on observes only the apps explicitly selected under Apps under observation.
- Explorer notifications have their own toggle and default off. Turning them off does not disable Link Guard, threat protection, Child Safety, or existing manual domain rules.
- Continuous observation keeps only selected apps' Link Guard warning destinations. Ordinary allowed-destination capture remains limited to the explicit 10-minute Learning Mode so QuietShield does not become an all-app continuous traffic recorder.
- After Block, Remove block, Try once, temporary allow, permanent allow, or app-specific allow actions, the destination action pop-up closes instead of leaving stale controls over the refreshed list.
- Saved Connection Explorer domain rules are re-read before success is reported, so a historical Allowed event cannot be mistaken for the current rule state.
- Connection Explorer remains in the Protection section. The Settings search icon continues to search the whole QuietShield app.
- Connection Explorer is now one of the optional customizable Quick Access shortcuts and can be added, removed, or reordered like other optional shortcuts.
- System-wide Link Guard and security blocking remain active even when Connection Explorer observation or Explorer notifications are off.
- Connection Explorer is now opt-in and app-scoped. Security protection remains active independently of Explorer observation notifications.

## 2.9.20 — Code346

**Link Guard, sensitive-content protection, and Connection Explorer**

- • Adds system-wide Link Guard for suspicious destinations from any app.
• Adds stricter gambling and adult/explicit protection.
• Adds advanced per-app Connection Explorer and Learning Mode.
• Adds File Link Guard and compact App Connection Lock choices.
- Link Guard evaluates observable destination hostnames from any protected app, including apps with built-in browsers. Known threat lists remain authoritative; conservative local heuristics warn or block strong phishing-impersonation patterns.
- QuietShield does not install a new HTTPS interception certificate. Full URL/path analysis remains limited to places where QuietShield legitimately receives the complete URL, such as Private Browser or a URL shared to QuietShield.
- Adult/admin false-positive recovery for local Link Guard heuristics includes Try once, 10-minute allowance, and permanent per-app exception. Managed-child devices do not expose these bypasses.
- Sensitive Content separately handles gambling/betting and adult/explicit destinations. Explicit anime/manga identifiers are included, but ordinary anime/manga is never blocked merely because of its art style.
- Connection Explorer lets advanced users review exactly attributed destinations, use a 10-minute Learning Mode, create app-specific or global domain/subdomain blocks, and undo the last app-specific manual rule.
- Every manual Connection Explorer block warns that sign-in, notifications, media, sync, payments, maps, or the app's entire Internet connection may stop working.
- File Link Guard checks hyperlinks in files the user explicitly selects or shares. It uses bounded local parsing and never modifies the selected file.
- App Connection Lock uses shorter one-row choices so all four connection modes remain readable in the selection dialog without the previous text crowding.
- Code345 Strict App Shield, troubleshooting and App privacy report remain included, while threat, Child Safety, parent rules and critical-package safeguards retain priority.
- Advanced destination blocking can break apps. QuietShield warns before manual blocks and keeps an Undo path for recent app-specific rules.

## 2.9.19 — Code345

**Strict App Shield for apps that need stronger privacy**

- • Adds optional Strict App Shield for individual apps.
• Warns clearly that aggressive blocking can break app features.
• Adds per-app troubleshooting and explainable blocked destinations.
• Turns Tracker intelligence into a local-only App privacy report.
- Normal App Ad Protection stays the recommended default. Strict App Shield is an explicit per-app option, not a new global default.
- Strict App Shield blocks known ads, ad measurement, analytics, attribution, telemetry, social tracking, engagement, performance/session-replay trackers, strict tracker domains and enabled downloaded ad/tracker packs for the selected app.
- Before enabling it, QuietShield warns that sign-in, notifications, purchases, media, maps, synchronization, rewards or other online features may stop working.
- Troubleshoot opens that app's filtered Activity timeline so blocked destinations and reasons can be reviewed without weakening other apps.
- Per-destination troubleshooting supports permanent per-app allowance, a 10-minute ad compatibility allowance, Keep blocked, and returning a strict app to normal protection.
- The App privacy report remains local-only and now shows Strict App Shield usage alongside tracker trends, companies and purposes.
- Threat, Child Safety, imported protection and explicit parent block rules retain priority; CriticalPackageGuard and FileSafety behavior are unchanged.
- Strict App Shield is intentionally aggressive. Use it only for apps where maximum tracker blocking matters more than compatibility.

## 2.9.18 — Code344

**Canonical Code343 repairs delivered as a new update**

- • Delivers the corrected Settings magnifying-glass search icon.
• Keeps Incognito and Website view available throughout Private Browser.
• Keeps .qs restore-file opening with confirmation, authentication and rollback protection.
• Carries forward CriticalPackageGuard and the verified system-package safety repair.
- Uses versionCode 344 so devices that already received the earlier public Code343 build can receive this canonical repair normally.
- Carries forward the geometry-drawn Settings/Protection magnifying glass instead of the blank font-dependent circle.
- Carries forward global Private Browser Incognito and Website view controls and the repaired URL/search field.
- Carries forward QuietShield .qs file opening with explicit restore confirmation, parent authentication, rollback protection and structured JSON compatibility.
- Carries forward CriticalPackageGuard protection for HOME launchers, Samsung One UI Home, System UI, Settings, Android core and QuietShield itself.
- Retains Web Shields, FileSafety protections, Code342 search improvements, update attention, dialog contrast and compact Private Browser controls.
- This release changes the update identity, not the security design: the verified canonical Code343 source is carried forward to Code344.

## 2.9.17 — Code343

**Critical restore, system safety and interaction repairs**

- • Prevents failed Backup & Restore operations from leaving a partially restored portable configuration.
• Protects HOME/SystemUI package availability behind the centralized CriticalPackageGuard.
• Fixes the Private Browser address bar and keeps Incognito + Website view available from every PB menu surface.
• Replaces the blank Settings search circle with a persistent geometry-drawn magnifying glass.
• Opening a QuietShield .qs backup from Android Files now opens QuietShield and asks before restoring it.
- Creates a portable safety snapshot before restore and rolls back that snapshot if restore fails.
- Accepts supported legacy string-wrapped JSON only where the restore code explicitly expects an object or array; malformed values fail with a clear message instead of a raw Java/JSON exception.
- Adds CriticalPackageGuard protection for the active/default HOME launcher, all installed HOME-capable launchers, Samsung One UI Home, System UI, Settings, Android core, and QuietShield itself.
- Audits active source for package hide/suspend/disable/component-disable paths and records an A/B/C root-cause classification before publication.
- Keeps Nova or another third-party launcher free to remain the default HOME app; the safety guard does not change the default launcher.
- Fixes the Private Browser address field obstruction by giving Web Shields one fixed toolbar cell while the URL/search field receives the remaining width.
- Replaces the font-dependent Settings/Protection search glyph with a Canvas-drawn magnifying glass styled like QuietShield semantic Quick Action icons.
- Keeps Turn on/off Incognito and Website view available from the Private Browser menu whether Home or a webpage is currently shown.
- Registers QuietShield backup file opening so supported .qs files can launch QuietShield, show an explicit restore confirmation, require parent authentication, and use the same rollback-protected restore path.
- Code342 search, green update attention, bullet Update Log, dialog contrast, compact PB controls, Code340 Web Shields, FileSafety protections, signing and updater-last release safety are retained.

## 2.9.16 — Code342

**Search, update clarity, and compact browser controls**

- • Search aggressive apps directly inside Aggressive ads & trackers.
• Verified update attention now uses a green Settings outline instead of blue.
• What’s New and Update Log summaries use readable bullet lists.
• Got it and other primary dialog actions keep solid high-contrast text after the dialog attaches.
• Private Browser icons are back to compact 20dp visual proportions while keeping large touch targets.
- Search aggressive apps directly inside Aggressive ads & trackers.
- Verified update attention now uses a green Settings outline instead of blue.
- What’s New and Update Log summaries use readable bullet lists.
- Got it and other primary dialog actions keep solid high-contrast text after the dialog attaches.
- Private Browser icons are back to compact 20dp visual proportions while keeping large touch targets.
- Protection, Web Shields, FileSafety checks, signing, and updater safety behavior are retained.

## 2.9.15 — Code341

**Private Browser interaction and theme polish**

- • Improved Update Log and primary dialog action contrast across QuietShield themes.
• Replaced font-dependent Private Browser toolbar glyphs with persistent semantic Canvas icons, including Search History.
• Made Speed Dial folder creation easier with a wider merge target, shorter dwell, and drop-time fallback.
• Replaced the oversized reorder line with a compact cell-sized outline and removed permanent Speed Dial helper text.
• Anchored Private Browser Settings above the bottom-right menu control as an animated speech-bubble panel.
• Added smooth QuietShield ↔ Private Browser fade transitions while retaining Web Shields and security behavior.
- Improved Update Log and primary dialog action contrast across QuietShield themes.
- Replaced font-dependent Private Browser toolbar glyphs with persistent semantic Canvas icons, including Search History.
- Made Speed Dial folder creation easier with a wider merge target, shorter dwell, and drop-time fallback.
- Replaced the oversized reorder line with a compact cell-sized outline and removed permanent Speed Dial helper text.
- Anchored Private Browser Settings above the bottom-right menu control as an animated speech-bubble panel.
- Added smooth QuietShield ↔ Private Browser fade transitions while retaining Web Shields and security behavior.

## 2.9.14 — Code340

**Web Shields for Private Browser**

- QuietShield 2.9.14 upgrades Private Browser to a general-purpose Web Shields model: Balanced, Enhanced, and Custom protection profiles; per-site on/off and saved settings; ad, tracker, pop-up, tracking-script, cryptomining, tracking-parameter, and cosmetic filtering controls; existing signed filter lists and blocked counters; and the same shield engine on every website rather than a separate YouTube-labeled ad blocker. Code339 Speed Dial folders, theme and emoji cleanup, Aggressive ads & trackers, update attention, and retained security behavior remain unchanged.

## 2.9.13 — Code339

**Cleaner themed interface and Speed Dial folders**

- QuietShield 2.9.13 makes nested cards fully theme-aware, removes emoji decorations across app text including Parent Command Center, keeps Home Quick Action semantic icons while other feature rows stay text-first, adds an Aggressive ads & trackers app-list entry, and upgrades Private Browser Speed Dials with smooth press-and-hold rearranging, a subtle insertion line, drag-to-folder creation, renamable folders, four-item folder previews, and animated folder pop-outs. Verified-update attention, Private Browser History Search, and retained security behavior remain unchanged.

## 2.9.12 — Code338

**QuietShield 2.9.12 update**

- Home Quick Actions restore semantic icons that match each function, while QuietShield's content and settings surfaces stay clean and text-first.

1. App Lock and every selected Home Quick Action use the authoritative QuietShield feature-icon registry so the icon matches the feature's actual function.

2. Internet Rules uses the rules icon, Mobile Data uses the cellular-data icon, Wi-Fi Safety uses the Wi-Fi safety icon, App Updates uses the update icon, Premium uses the premium icon, Allow / Block uses its policy icon, Compatibility uses the compatibility icon, and the same semantic mapping applies to the remaining supported Home shortcuts.

3. Family and safety, Protection setup, and Help and maintenance now keep the same full-size row title and summary typography as the rest of Settings. A stale legacy child-removal workaround no longer strips the title from text-only rows.

4. Legacy decorative feature glyphs are removed from Main Settings/action content. Home Quick Actions, primary navigation, the QuietShield protection logo, Quick Settings, search, and essential Private Browser controls remain intentional functional-icon exceptions.

5. The saved Quick Access selection and order remain authoritative, with App Lock fixed first. Code337 persistent skipped-update Settings attention, Code336 Data Saved > and dialog typography, Code335 Settings cogwheel, Code334 Android 16 dialog hardening, Code333 global Private Browser History Search, signing/updater verification, and retained protection/security behavior remain preserved.
- QuietShield 2.9.12 / Code338

## 2.9.11 — Code337

**QuietShield 2.9.11 update**

- QuietShield now uses a cleaner text-first feature interface while keeping essential navigation and browser controls clear.

1. Feature and decorative icons are removed from main QuietShield content surfaces, including Home Quick Actions, Protection, Activity, Settings action rows, and Edit Quick Access. The existing primary navigation controls remain icons for navigation clarity, and Quick Settings keeps its dedicated feature icon.

2. If a verified newer QuietShield release remains available after the user intentionally or accidentally leaves the update screen, the Settings navigation control keeps a visible update-attention glow.

3. When a newer verified release is available, Settings shows an Update available notice at the top with an Open update button that goes directly to the App Updates section. The notice and glow are hidden automatically when the installed version is current.

4. Private Browser menu/action labels are simplified to text-first presentation while essential browser controls remain available.

5. Bundled What's New and Update Log history is normalized to detailed text-first summaries without per-item icon cards.

6. Code336 Data Saved > and dialog typography, Code335 Settings cogwheel and Quick Access cleanup, Code334 Android 16 dialog lifecycle hardening, Code333 global Private Browser History Search, release signing, updater verification, and retained protection/security behavior remain preserved.
- QuietShield 2.9.11 / Code337

## 2.9.10 — Code336

**QuietShield 2.9.10 update**

- Polishes Protection rows, dialog action typography, and the Home Data Saved click cue.

1. Protection: App Ad Protection, Internet Access, Compatibility exclusions, and Tracker details no longer show redundant circular leading controls; the full row remains tappable.

2. Dialog actions: Done and other primary dialog buttons use the same bold, high-contrast QuietShield button typography and theme treatment instead of a washed-out platform appearance.

3. Home: Data Saved is now labeled Data Saved > so users can immediately see that the statistic opens the Data savings report.

4. Code335 Quick Access cleanup and Settings cogwheel, Code334 Android 16 dialog lifecycle hardening, Code333 global Private Browser History Search, semantic icons, signing, updater verification, and retained protection/security behavior remain preserved.
- QuietShield 2.9.10 / Code336

## 2.9.9 — Code335

**QuietShield 2.9.9 update**

- Polishes the Update Log, Quick Access labels, and primary navigation icon consistency.

1. Cleaner update pop-up: release notes use a short phone-safe title and a detailed text list instead of narrow ACT/NAV/PB/LOG/FIX text-badge cards that wrapped and looked like broken icons.

2. Quick Access: duplicate emoji/glyph prefixes are removed from feature titles. The existing semantic vector icon remains the single icon for Mobile Data Watch, Wi-Fi Safety, Parent PIN, Trusted websites, File & APK Check, Aggressive App Watch, How QuietShield Works, Support, Pending errors, and the other shortcuts.

3. Settings navigation: the primary Settings destination now uses a true cogwheel instead of the sun/theme glyph.

4. Update Log history: Code326-Code334 bundled notes are normalized to the same badge-free detailed presentation so older entries stay readable.

5. Code334 Android 16 dialog lifecycle hardening, Code333 global Private Browser History Search, semantic feature icons, updater verification, signing, and retained protection/security behavior remain unchanged.
- QuietShield 2.9.9 / Code335

## 2.9.8 — Code334

**QuietShield 2.9.8 update**

- Cleans the Activity dashboard, simplifies primary navigation, restores detailed Update Log entries, and hardens dialog window lifecycle handling.

1. Cleaner Activity rows: Full activity log, Tracker insights, Network intelligence, and Data savings report no longer show the redundant left circular control.

2. Icon-only primary navigation: Home, Protect, Private Browser, Activity, and Settings use semantic icons only; visible labels are removed while accessibility labels/tooltips remain.

3. Minimal PB navigation icon: Primary navigation uses a clean browser vector instead of the branded PB image.

4. Detailed Update Log restored: Code326-Code334 release-note assets use the full structured schema so Update Log explains what changed instead of appearing empty.

5. Android 16 dialog hardening: Dialog window sizing now checks showing/attached state and avoids stale window mutations that can trigger WindowManagerGlobal IllegalArgumentException.

6. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

7. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.8 / Code334

## 2.9.7 — Code333

**QuietShield 2.9.7 update**

- Standardized feature icons across QuietShield and made Private Browser History Search available throughout PB.

1. One semantic icon system: Home Quick Actions and Settings resolve the same feature to the same premium vector icon.

2. Correct Mobile Data icon: Mobile Data uses a true cellular-data vector instead of a percentage-like or unrelated glyph.

3. History Search everywhere: History Search is available from PB Home, webpages, tabs, menu, managers, Settings, and the in-app PDF reader.

4. PB branding retained: Private Browser continues to use its supplied branded artwork outside the simplified primary navigation introduced in Code334.

5. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

6. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.7 / Code333

## 2.9.6 — Code332

**QuietShield 2.9.6 update**

- Fixed Home Quick Actions, introduced the glass QuietShield protection toggle, and polished backup/help/footer behavior.

1. Quick Actions follow your choices: Home reflects the shortcuts selected by the user in saved order.

2. App Lock replaces Profiles: App Lock opens App Connection Lock instead of routing to generic Settings.

3. Glass protection toggle: The QuietShield hero logo is an animated protection ON/OFF control.

4. Simpler backup wording: Settings shows Create backup file and Restore backup without exposing the internal file suffix.

5. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

6. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.6 / Code332

## 2.9.5 — Code331

**QuietShield 2.9.5 update**

- Removed unnecessary left circular glyph controls from selected Settings sections while keeping whole rows tappable.

1. Family and safety: Leading circular controls were removed from Family and safety action rows.

2. Protection setup: Leading circular controls were removed from Protection setup rows.

3. Help and maintenance: Leading circular controls were removed from Help and maintenance rows.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.5 / Code331

## 2.9.4 — Code330

**QuietShield 2.9.4 update**

- Improved tablet responsiveness, anti-clipping behavior, typed-only PB history suggestions, and webpage chrome fading.

1. Responsive navigation: Tablet navigation keeps Private Browser readable with responsive rail sizing.

2. Typed-only suggestions: History suggestions appear only after typing/editing and remain below address actions.

3. More address-bar room: Back, Forward, Refresh, and Shields fade away on webpages and return on PB Home.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.4 / Code330

## 2.9.3 — Code329

**QuietShield 2.9.3 update**

- Added daily Data Saved, cleaner Private Browser Home behavior, contextual webpage tools, and a warm off-white Light theme.

1. Daily Data Saved: Home shows the current local-day saved-data estimate and opens Data Savings when tapped.

2. Context-aware tools: PB Home hides webpage-only actions and reveals them only on real webpages.

3. Warm Light theme: Light mode uses a warm dirty-white palette with readable dark text and controls.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.3 / Code329

## 2.9.2 — Code328

**QuietShield 2.9.2 update**

- Polished the futuristic GUI with cleaner Speed Dials, aligned theme controls, and simpler action/navigation rows.

1. Opera-style Speed Dials: Speed Dials emphasize circular site icons/favicons without heavy dark pads.

2. Cleaner settings: Repeated branding and redundant Settings introduction text were removed.

3. Navigation polish: Quick Action labels and dashboard navigation alignment were refined.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.2 / Code328

## 2.9.1 — Code327

**QuietShield 2.9.1 update**

- Refined the Code326 foundation to more closely match the approved QuietShield concept while preserving Android behavior.

1. Unified themes: System, Dark, AMOLED, and Light use one coordinated QuietShield design language.

2. Protection hero: The Home hero and protection statistics became more compact and glanceable.

3. Browser consistency: Private Browser chrome, cards, Speed Dials, and tablet layouts follow the active theme.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.1 / Code327

## 2.9.0 — Code326

**QuietShield 2.9.0 update**

- Major QuietShield visual overhaul based on the approved futuristic modern minimal direction.

1. Protection Dashboard: Introduced the card-based Protection Dashboard shell with cleaner hierarchy and responsive phone/tablet spacing.

2. Private Browser refresh: Private Browser Home and circular Speed Dials were rebuilt to match the new QuietShield visual language.

3. Cleaner controls: Protection choices, overflow menus, and shared surfaces moved to a more consistent modern card system.

4. Existing QuietShield protection, privacy, authentication, signing, updater verification, and retained Private Browser behavior remain preserved unless explicitly listed above.

5. AAB and R8 mapping remain private release artifacts; Android and Google Play Protect installation scanning are not bypassed.
- QuietShield 2.9.0 / Code326

## 2.8.4 — Code325

**QuietShield 2.8.4 update**

- QuietShield 2.8.4 makes Private Browser denser and easier to recover from mistakes, improves tablet logo rendering, defaults the managed-child first-setup tracker alert to off, and automatically reconnects protection after filtering changes.

1. Portable backup retained: Portable .qs backups, pinch zoom and adaptive tablet address-bar page tools from Code324 remain intact.

2. No Back-button apply prompt: Back navigation no longer asks Apply protection changes before leaving; any still-pending debounce is flushed automatically.

3. Protection applies automatically: Balanced, Battery Saver, Strict, DNS provider and other reconnect-required settings save immediately, debounce rapid selections, and reconnect once when protection is already on.

4. Child first-setup default: On a managed child's first setup, the new-tracker notification checkbox starts untoggled. Existing completed setups keep their stored choice.

5. Sharper tablet branding: In-browser QuietShield/PB UI uses the supplied high-resolution logo source, and density mipmaps are regenerated with high-quality downsampling for cleaner tablet rendering.

6. Cleaner browser Settings: The 3-dot surface is titled Settings ⚙️, uses tighter grouped rows, and keeps the existing page, privacy, video and browser controls.

7. Restore closed tabs: A closed tab is kept only in session memory. The 3-dot Settings menu offers Reopen closed tab and Recently closed without adding it to persistent browsing history.

8. Compact circular Speed Dials: Speed Dials now use a dense circular launcher layout with more columns on phones and tablets instead of large square cards.

9. Recently closed tabs are session-only and are cleared across normal/incognito profile changes.

10. Changing a protection setting never turns protection on when the user has it disabled; the value is saved for the next start instead.

11. FileSafetyScanner scoring and thresholds, FileSafetyActivity retained source, YouTube-specific ad suppression, signer identity, Play Protect behavior, AAB privacy and updater-last publication are unchanged.

12. Every public repository release must advance both versionName and versionCode; Code325 is 2.8.4 and will not reuse 2.8.3/324.
- Smaller browser UI, safer recovery, fewer extra taps.

## 2.8.3 — Code324

**QuietShield 2.8.3 update**

- QuietShield now combines responsive dialogs with a portable .qs backup container, square Private Browser speed dials, pinch zoom, and adaptive page-tool buttons on wider tablet windows.

1. Adaptive page tools: Wide Private Browser windows place Snapshot, Find in page, Save as PDF and Save offline beside the address bar; compact tablets show only the tools that fit and phones stay uncluttered.

2. Pinch to zoom: Web pages use Android WebView's built-in pinch zoom. Two-finger gestures now take priority over pull-to-refresh and the tab zoom state follows scale changes.

3. Square Speed Dials: Private Browser Speed Dial tiles are measured as true squares on phones, tablets, landscape and split-screen windows.

4. Portable .qs backups: New backups use the .qs extension and a UTF-8 JSON container with an explicit QuietShield schema that future Android TV and Windows clients can read. Legacy JSON backups remain importable.

5. Code323 browser features retained: Default-browser support, PB shortcut, PDF reader, downloads, omnibox, search engines, History controls, Offline Pages, Backup Format 8 and the supplied QuietShield/PB logos remain intact.

6. Buttons stay readable: Dialog and in-dialog buttons remain single-line where possible, with better minimum heights and spacing so labels such as Open, Delete, Today and 2 months do not break into stacked letters.

7. Double-padding bug fixed: Dialog content no longer reapplies full-tablet screen centering inside an already centered popup, fixing the narrow Search, History and Offline Pages layouts seen on tablets.

8. Tablet-aware sizing: Dialog width is calculated from the current Android window configuration, so portrait, landscape and split-screen layouts remain comfortable without becoming desktop-sized.

9. Modern QuietShield dialogs: Raw gray AlertDialogs now use a rounded QuietShield card with stronger hierarchy, readable actions, consistent light/dark styling, and a top-right × for Close-only informational windows.

10. The responsive dialog treatment is applied mechanically to Kotlin AlertDialog constructors throughout the app, while payload-managed main/PB dialogs are hash-verified directly.

11. Dialog source changes are backed up and restored automatically if the Code324 build fails before artifact verification.

12. No FileSafety scoring, YouTube-specific ad handling, signer identity, AAB privacy, Play Protect behavior or updater-last publication order is weakened.

13. The .qs container remains JSON-based and self-describing so future QuietShield platform readers can ignore unsupported sections without depending on Android object serialization.

14. Adaptive toolbar decisions use current screenWidthDp and refresh on configuration changes, including rotation and split-screen resizing.
- One QuietShield release: responsive, portable and tablet-aware.

## 2.8.2 — Code323

**QuietShield 2.8.2 update**

- QuietShield Private Browser becomes a sharper, more personal everyday browser with its own identity, Android default-browser support, direct launcher access, smart downloads/file opening, an in-app PDF reader, configurable search, smarter history, offline reading, resumable downloads, child-safe search behavior, and Backup Format 8.

1. Backup Format 8: Backs up the complete portable user configuration plus bookmarks, surviving normal Private Browser history, search engines, offline pages, and the PDF-opening preference while credentials and runtime state stay device-local.

2. History + offline reading: Search titles and complete long URLs, use day/week/month deletion scopes, and save safe text reading copies for offline access.

3. Real omnibox + search engines: The address bar understands websites and searches. DuckDuckGo is the default, Brave Search and Google are built in, and validated custom HTTPS engines can be added.

4. QuietShield PDF Reader: Downloaded PDFs can open inside Private Browser's native PDF reader, with page navigation, sharing and an Open with app option.

5. Download center + file opening: A download icon appears while transfers run. Completed downloads show a blue dot until opened, and Android chooses the installed app for DOCX, ZIP, media and other file types.

6. Default browser + direct shortcut: Private Browser can request Android's default-browser role and can add its own Home-screen shortcut. Android and the launcher still ask for user approval.

7. Sharper QuietShield + PB identity: The app logo is cleaned for clearer phone/tablet rendering, while Private Browser gets its own matching icon for browser and shortcut surfaces.

8. Incognito history is never recorded or backed up.

9. Deleting history before creating a backup means those deleted visits are not included.

10. Custom search engines must use HTTPS and a %s query placeholder.

11. Backup filenames retain the date and time for easy identification.

12. License secrets, parent PIN material, tokens, cookies, sign-in sessions, device identity, signing material, transient diagnostics, and active VPN runtime state remain excluded from portable backup.

13. Code322 strict PB blocking/page tools/GUI/DNS/data-savings work and Code321 resilience protections are retained.

14. Android default-browser selection and launcher-pinned shortcuts are system-owned choices and require user consent again after a device reset; QuietShield does not silently restore them.

15. Download-center notification state is runtime-only and is intentionally not part of portable Backup Format 8.
- Personal where it should be, strict where safety matters.

## 2.8.1 — Code322

**Browser strictness + UX & insights**

- Stricter Private Browser ad cleanup, cleaner navigation, clearer DNS status, richer page tools, and a new local data-savings report.
- Stricter Private Browser: Adds a short document-start cosmetic guard before page scripts, while retaining request-level blocking, signed Shields rules, and bounded DOM cleanup to reduce ad flashes.
- New page tools: Zoom, Find in page, local extractive Summarize, Android Translate, Save as PDF, and visible-page Snapshot are now grouped in Private Browser.
- Data savings report: Activity & Insights now shows estimated daily and monthly data savings with a local 2-month history and no website or DNS history.
- Cleaner whole-app search: Home, Apps, and Settings use a compact magnifying-glass action beside the page title instead of a permanent search box.
- DNS status that explains itself: Home shows the selected provider immediately and separately identifies the effective active DNS when Child Safety changes it.
- Private Browser Speed Dials are more compact while retaining touch-friendly tiles.
- Private Browser is no longer duplicated in Protection Center or Quick Access explanatory copy.
- Backup exports use a filename that includes the date and time.
- The post-update summary renders structured highlight cards instead of plain bullet text.
- The update screen now explains that Android or Google Play Protect may still scan the verified APK during installation.
- Code321 boot/ANR, VPN resilience, File & APK Check scoring, Family policy, and signer continuity are retained.
- Stricter where protection matters, quieter where navigation should stay simple.

## 2.8.0 — Code321

**Core resilience suite**

- Whole-app reliability and security improvements for startup, VPN health, network changes, app updates, diagnostics, and signed endpoints.
- VPN health you can trust: QuietShield now tracks requested, starting, establishing, protected, degraded, recovering, and failed runtime phases instead of relying on one stale state.
- Safer restart recovery: Repeated boot/VPN instability temporarily defers only noncritical maintenance while core protection recovery keeps running.
- Protection self-test: Run local checks for VPN permission, engine readiness, network validation, App Connection Lock, component exposure, and recent startup instability.
- App change watch: A silent daily baseline notices meaningful signer or sensitive-permission changes after app updates without continuous scanning.
- Smarter network guard: Foreground event-driven warnings identify captive portals and loss of validated Internet access without polling.
- Signed Browser Shields update redirects remain HTTPS-only and bounded.
- Memory pressure trims caches without unloading active protection policy.
- No new continuous scanner or periodic Wi-Fi scan is added.
- Private Browser and YouTube-specific ad suppression are unchanged.
- Core protection first. QuietShield keeps routine monitoring event-driven and low-noise.

## 2.7.24 — Code320

**Whole-App Stability + Boot Recovery**

- Hardens QuietShield startup after phone restarts and reduces main-thread work across the protection service.
- Faster restart recovery: Boot recovery is moved off the main thread and avoids duplicate VPN starts while Android is restoring Always-On protection.
- Protection starts first: The VPN service enters foreground state quickly, then performs heavier initialization on QuietShield's serialized background lifecycle worker.
- Local failure diagnostics: On Android 11 and newer, QuietShield can record a sanitized local reason for a previous ANR, crash, low-memory exit or startup failure.
- Defers noncritical update, license and Family maintenance until after the boot-critical protection window.
- Moves recurring VPN health, entitlement and App Connection Lock checks away from the UI/main thread.
- Uses bounded recovery delays instead of an unlimited restart loop.
- Private Browser, File & APK Check scoring, VPN filtering rules and YouTube-specific behavior are unchanged by Code320.
- Code320 focuses on whole-app stability and protection recovery, especially after device restarts.

## 2.7.23 — Code319

**Browser Threat Guard 2.0**

- Adds another local phishing/deceptive-address layer without background scanning or cloud URL lookups.
- Look-alike domain checks: QuietShield can warn when a domain mixes writing systems or uses other deceptive address structures.
- Runs only when navigating: The check runs only for a top-level page address, so there is no continuous scanner.
- Existing Safe Browsing retained: WebView Safe Browsing, mixed-content blocking and hardened file/content access remain enabled.
- Retains existing Punycode, embedded-credential, direct-IP and complex login/account URL warnings.
- Adds mixed Latin/Cyrillic/Greek look-alike detection locally.
- Does not upload browsing addresses and adds no periodic background work.
- YouTube-specific ad suppression is unchanged.
- Threat Guard is an additional local warning layer; it does not guarantee a website is safe.

## 2.7.22 — Code318

**Clearer File & APK Check**

- QuietShield 2.7.22 makes File & APK Check calmer and clearer while preserving Android's normal APK-install path and QuietShield's existing local risk engine.
- Clearer results: LOW, CAUTION, and HIGH are presented as No obvious risks found, Review recommended, and High-risk indicators detected.
- Optional local check: Files are checked only when you choose or share them with QuietShield. The file stays on your device.
- Normal APK opening unchanged: QuietShield already does not own the general APK-open path. Android's package installer and Play Protect remain separate.
- Risk engine unchanged: FileSafetyScanner scoring, permission/signature inspection, and CAUTION/HIGH thresholds are not weakened.
- Renames and reframes the scanner as File & APK Check so a scan result is not mistaken for a malware verdict.
- Shows No obvious risks found instead of a broad safe claim and states that a local result does not guarantee a file is safe.
- Shows Review recommended for caution-level findings and High-risk indicators detected for high-risk findings.
- Explains that QuietShield File Check is local and separate from Google Play Protect.
- Keeps Android Share and deliberate in-app File & APK Check access; normal APK opening remains on Android's existing installer path.
- Does not weaken FileSafetyScanner scoring, APK permission/signature inspection, or CAUTION/HIGH findings.
- Retains Code317 Android 16 Back hardening, Code316 backup/update-log work, Code315 Private Browser downloads, VPN/firewall, Family protection, signed Browser Shields, licensing, and signer continuity.
- YouTube-specific ad suppression is intentionally unchanged.
- QuietShield File Check is an additional local safety layer. It does not replace Google Play Protect and cannot guarantee that a file is safe.

## 2.7.21 — Code317

**Android 16 back navigation hardening**

- QuietShield 2.7.21 makes the main Protection Center use one consistent Back path on Android 16 and older Android versions while preserving the existing double-back exit guard and unsaved protection-change prompt.
- Back works consistently: Android 16 predictive Back and the older Back fallback now use the same QuietShield navigation decision path.
- Protection changes stay safe: If protection settings still need to be applied, Back shows the existing apply-before-leaving choice instead of bypassing it.
- Double-back exit retained: With no pending protection changes, the first Back press still prompts and the second backgrounds QuietShield instead of immediately finishing the main screen.
- Legacy behavior audited: The release publisher checks that legacy Back handling is limited to approved fallbacks that also have Android 13+ predictive-Back callbacks.
- Fixes a Code316 routing mismatch where MainActivity's Android 13+ OnBackInvoked callback could finish the Activity immediately while the legacy onBackPressed path used QuietShield's double-back home guard.
- Makes pending protection-setting changes take priority on both predictive and legacy Back paths, preserving the existing Apply and leave / Leave without applying / Keep editing choices.
- Stores and unregisters the MainActivity OnBackInvokedCallback so Activity teardown does not leave a stale callback reference.
- Adds a pure MainBackNavigationPolicy regression test and a publisher audit that rejects unapproved KEYCODE_BACK use or new legacy onBackPressed handlers without a predictive-Back bridge.
- Retains Code316 professional What's New/Update Log and backup portability, Code315 Private Browser downloads, Code312 browser media continuity, signed Browser Shields, Family protection, VPN/firewall behavior, and signer continuity.
- YouTube-specific ad suppression is intentionally unchanged in this release; Play-specific decisions remain deferred until the Google Play/D-U-N-S submission phase.
- No VPN/filtering, licensing, Family, download, or YouTube-specific filtering behavior is changed by this Android 16 navigation release.

## 2.7.20 — Code316

**Polished updates + stronger backups**

- QuietShield 2.7.20 replaces the plain-text update experience with a cleaner What's New design and makes App Connection Lock and Compatibility choices more explicitly portable between phones.
- Professional What's New: Updates now open with a compact, polished card layout instead of a wall of technical text. Full details remain available when you want them.
- Cleaner update history: Settings > Update log now uses release cards with version, title, summary, and an expandable detail view.
- System-app rules backed up: App Connection Lock now explicitly carries non-default rules for system apps, including system apps you blocked, while still refusing unsafe essential-system restrictions on the destination phone.
- Compatibility choices backed up: Manual exclusions, automatic compatibility opt-outs, and portable Compatibility settings are captured in a dedicated backup section and restored as part of the same settings backup.
- The automatic post-update experience is now a custom themed What's New layout with a shield header, version chip, compact highlight cards, and an optional technical-details section.
- The persistent Update log now shows a chronological card list instead of a plain selection list, while remaining fully local to APK-bundled release-note assets.
- Protection/service status messages that arrive while release notes are open are deferred until the release UI closes so they do not cover the update content.
- App Connection Lock backup schema advances to schema 3 and explicitly stores non-default system-app policies in addition to the complete historical policy map and profile systemPolicies.
- Blocked and Wi-Fi-only system-app choices remain portable by package name; on restore, essential system packages on the destination phone are still protected from unsafe blocking.
- Compatibility backup now has a dedicated structured snapshot for manual bypass packages, automatic opt-out packages, compatibility guard settings, and safe compatibility_* preferences, while runtime notices/counters/timestamps stay device-local.
- The existing Format 7 portable settings snapshot remains in place for backward compatibility and broad portable coverage.
- Retains Code315 fast Private Browser downloads, Code314 GUI stabilization and persistent update history, Code312 tab/media continuity, Code311 complete portable Backup & Restore, signed Browser Shields, Family protection, App Connection Lock, VPN/firewall, and updater signer continuity.
- Device-bound credentials, licensing/device identity, parent PIN material, certificate installation state, cookies, website sign-ins, session storage, and current VPN runtime state remain intentionally excluded from portable backups.

## 2.7.19 — Code315

**Fast Private Browser downloads**

- QuietShield 2.7.19 adds an app-owned high-throughput Private Browser downloader that saves completed files directly to the public Downloads folder while preserving Code314 GUI stabilization and the persistent Update log.
- Private Browser can now download normal HTTP and HTTPS files directly inside QuietShield and save completed files to the device Downloads folder.
- Android 14 and newer use the platform HttpEngine fast path with HTTP/2 and QUIC enabled; Android 10-13 use the secure platform URLConnection fallback.
- Downloads stream to storage with a bounded buffer instead of loading the full file into memory, with at most two simultaneous transfers.
- Completed files are published through MediaStore.Downloads; incomplete transfers remain hidden and are removed if the transfer fails, with no legacy storage permission required.
- Authenticated downloads keep the browser User-Agent and original-host session headers where safe, but cookies and referers are never forwarded to a different redirect host.
- Every redirect is revalidated, HTTPS-to-HTTP downgrade redirects and unsafe non-network schemes are rejected, and filenames are sanitized before saving.
- Every download requires confirmation showing the filename, source site, and expected size when available.
- A Downloads action in Private Browser opens the device Downloads view when available.
- Retains Code314 icon-only phone navigation, distinct Browser hub actions, Site privacy manager, persistent Update log, Code312 tab/media continuity, and Code311 complete portable Backup & Restore.
- Downloads continue while the QuietShield process remains alive; this release does not claim resume-after-reboot or process-kill support.

## 2.7.18 — Code314

**GUI stabilization + persistent update log**

- QuietShield 2.7.18 polishes the new Protection Center, restores a reliable update log, and separates Private Browser actions so each control has a clear purpose.
- Phone bottom navigation is now icon-only so Browser and Settings no longer wrap or crowd the bar; full labels remain available to accessibility services and long-press tooltips, while tablet navigation keeps labels.
- Private Browser hub actions now use distinct icons instead of repeating the same globe icon.
- Site privacy & data is now a real separate function: it opens a current/recent-site chooser and then the selected site's Shields/data controls instead of duplicating Open Private Browser.
- Adds a persistent Update log under Settings so release notes can be reopened after installation instead of disappearing after the one-time post-update experience.
- Replaces the fragile post-update release-note trigger with a local APK-bundled release-notes center that shows once after a real app upgrade and does not repeatedly appear on every resume.
- The release-notes loader skips malformed optional historical entries instead of breaking the entire log.
- Site privacy launch is consumed only on a fresh Activity launch so rotation/configuration changes do not reopen the chooser repeatedly.
- Post-update notes wait for the main window to be foreground and focused, preventing update notes from colliding with startup routing, permission, or protection dialogs.
- Retains Code313 Protection Center navigation, Code312 Private Browser tab/media continuity fixes, Code311 complete portable Backup & Restore, signed Browser Shields, Family protection, App Connection Lock, VPN/firewall, and updater signer continuity.
- Final stabilization release. No device-bound credentials, browsing sessions, or private cookies are added to portable backups.

## 2.7.17 — Code313

**Protection Center GUI**

- New five-destination navigation: Home, Apps, Browser, Activity, and Settings.
- Home now includes a Protection Center overview for App protection, Private Browser, Family protection, and Network & DNS.
- Private Browser now has a dedicated hub for Shields/site data, trusted websites, protection filters, and browser activity.
- Quick Access is less cluttered because Private Browser moved to its own navigation destination while App Connection Lock stays pinned.
- Activity now surfaces the full log, Tracker Insights, and Network Intelligence together.
- All Code312 browser continuity fixes and Code311 complete portable Backup & Restore remain intact.

## 2.7.16 — Code312

**Quieter App Connection Lock + safer browser tabs**

- Stops repetitive App Connection Lock limitation dialogs while keeping routing health details available in QuietShield diagnostics.
- Fixes closing an accidentally opened Home tab so the surviving YouTube tab restores its real page instead of showing Speed Dials under the old tab title.
- Keeps media continuity when a new Home tab is opened accidentally and resumes a previously playing video when you return, without auto-playing videos that were already paused.
- Retains Code311 complete portable Backup & Restore, including App Connection Lock system-app selections and Compatibility settings.

## 2.7.15 — Code311

**Complete portable backup + App Connection Lock restore**

- QuietShield 2.7.15 expands Backup & Restore so portable user settings survive a move to another phone, including App Connection Lock system-app rules and Compatibility Exclusions.
- Backup format 7 captures all supported portable user-configurable AppPrefs values instead of relying only on the older fixed allow-list
- App routing selections, Compatibility Exclusions, automatic compatibility opt-outs and trusted Wi-Fi choices are included
- App Connection Lock now backs up its Block-all state, selected profile, Show system apps preference and complete per-app access map
- Explicitly blocked system apps in App Connection Lock are restored by package name when safe on the destination phone
- Custom App Connection Lock profiles retain safe package rules even when an app is not installed yet on the new phone
- Essential system apps on the destination device are never restricted by a restored portable rule
- Private Browser desktop mode, preferred video quality, pull-to-refresh and per-site Shields levels are included
- Portable fullscreen-video control preferences are included
- Internet Rules, bookmarks/Speed Dials, Quick Access, permanent app policies and protection-list sources remain included
- Device credentials, parent PIN secrets, license/family identity, VPN runtime state, certificate state, cookies, sign-in sessions and browsing history stay device-local for safety and privacy
- All Code310 Private Browser Shields, video reliability, Family, VPN, licensing and GUI improvements are retained
- Final release. Restore reproduces portable user settings without copying device-bound credentials or private browsing/session data.

## 2.7.14 — Code310

**Private Browser Shields + video reliability**

- QuietShield 2.7.14 finalizes signed Private Browser Shields, per-site cleanup and video playback usability improvements.
- Signed browser-filter update channel with last-known-good rollback
- Per-site Standard, Aggressive and Off protection levels
- Compact Shield button beside the address bar with blocked-request counts
- Separate ad, tracker, script and threat counters
- Selective per-site cleanup for cookies, QuietShield history, storage, location permission, form data and optional WebView cache
- Active video playback keeps the display awake instead of dimming or locking
- YouTube recommendation filter chips stop floating over the watch feed while video is playing
- Known HTML5 video controls fade smoothly after inactivity and return immediately on interaction
- Remote raw JavaScript is rejected; only sanitized cosmetic rules and audited scriptlet IDs are accepted
- Threat, Child Safety, imported and parent-defined blocking remain non-overridable
- All Code308 fullscreen, Family, VPN, backup and App Connection Lock improvements are retained
- Final release. The GitHub publisher keeps AAB and R8 mapping private and publishes the verified APK plus checksum only.

## 2.7.12 — Code308

**QuietShield 2.7.12 Code 308 Final**

- Backup and Restore format 6 now includes App Connection Lock custom profiles and the selected profile while excluding runtime state and without silently enabling App Connection Lock.
- The App Connection Lock profile editor remembers the Search user or system apps field as the active text owner so list refreshes, dialogs, and keyboard reappearance no longer return the cursor to Profile name.
- YouTube fullscreen restores QuietShield's ten-second side seek, Lock, brightness/volume gestures, Fit/Fill pinch, Smart Skip/status overlays, and other fullscreen tools removed by the Code307 diagnostic baseline.
- The previous synthetic YouTube settings-cogwheel click recovery is disabled because the same fullscreen gear failure was reproduced in other mobile browsers; QuietShield no longer tries to override that upstream mobile-web behavior.
- Fullscreen video now requests sensor landscape so normal and reverse landscape follow physical phone rotation even when Android auto-rotate is locked, where the device platform permits requested orientation.
- All Code307 protection, Family, GUI, VPN, browser privacy, restore-safety, and updater protections remain intact.

## 2.7.11 — Code307

**QuietShield 2.7.11 Code 307 Final**

- YouTube fullscreen now uses a website-native player surface with no QuietShield lock icon, ten-second seek handler, brightness/volume gestures, Fit/Fill pinch handling, Smart Skip overlay, status overlays, DOM touch probe, or cogwheel recovery script.
- The complete YouTube fullscreen MotionEvent stream is delivered through the normal WebView custom-view hierarchy before any QuietShield fullscreen gesture logic.
- Non-YouTube fullscreen sites retain the existing QuietShield fullscreen enhancements.
- The Private Browser refresh button remains beside the address field and the Browser-menu Reload item remains removed.
- All Code306 protection, Family, backup/restore, GUI, VPN, and browser privacy improvements are retained.

## 2.7.10 — Code306

**QuietShield 2.7.10 Code 306 Final**

- Fixes the remaining YouTube fullscreen settings-cogwheel problem by giving the lower player-control strip direct ownership of the complete Android touch sequence.
- The YouTube control strip now bypasses QuietShield pinch detection, side-seek detection, brightness/volume gesture arbitration, DOM control probes, and synthetic cogwheel recovery for ordinary one-finger taps.
- QuietShield still owns its visible Lock/Smart Skip controls, and a second pointer can still transition into the existing Fit/Fill pinch gesture.
- Retains the refresh button beside the address bar, history-only autosuggest, Speed Dial nickname/privacy improvements, modern GUI, backup safety, Family features, and VPN recovery.

## 2.7.9 — Code305

**QuietShield 2.7.9 Code 305 Final**

- Replaces the Code304 elementFromPoint-based YouTube settings fallback with a visible-settings-button rectangle match that is robust to WebView fullscreen compositing.
- The original website touch still reaches YouTube first. QuietShield intervenes only after a short delay and only when the tap matches the visible settings cogwheel.
- An already-open YouTube settings menu is never clicked again, preventing accidental open-then-close behavior.
- Retains the refresh button beside the address bar, history-only address suggestions, Speed Dial nicknames/privacy, fullscreen Fit/Fill pinch, side seek, brightness/volume gestures, and Lock.
- Retains the Code303 GUI hierarchy plus Code302/Code301 backup, protection, Family, Mobile Data Watch, and Android 16 VPN fixes.

## 2.7.8 — Code304

**QuietShield 2.7.8 Code 304 Final**

- Adds a dedicated Refresh button immediately to the left of the Private Browser address field and removes the duplicate Reload row from the Browser menu.
- Adds a targeted YouTube fullscreen settings-cogwheel recovery path: the original website tap always goes first, followed by a short delayed check that clicks only YouTube's own settings button if the settings menu did not open.
- The cogwheel fallback never performs a blind generic second click, so an already-open settings menu is not toggled closed.
- Captions, timeline, fullscreen exit, brightness/volume gestures, exact side seek, Fit/Fill pinch, Fullscreen Lock, history-only autosuggest, Speed Dial privacy/nicknames, and Incognito isolation remain intact.
- Retains the Code303 modern GUI hierarchy, restore-safe backup improvements, Android 16 VPN recovery, Family protections, and permanent signer requirements.

## 2.7.7 — Code303

**QuietShield 2.7.7 Code 303 Final**

- Removes emojis/icons from small section labels such as Family, Setup, Support, Connections & Data, Internet Rules & Lists, Backup & Recovery, and other grouping labels.
- Keeps icons on actionable rows and selected feature titles so the interface stays modern without looking repetitive or crowded.
- Uses distinct icons for adjacent concepts: Parent Command Center, Secure websites, Help and maintenance, Pending errors, and Quick Settings no longer reuse neighboring icons.
- Retains the Code302 modern lightweight GUI and Private Browser history-only autosuggest, Speed Dial privacy/nickname behavior, and all Code301 protection and backup improvements.

## 2.7.6 — Code302

**QuietShield 2.7.6 Code 302 Final**

- Private Browser address-bar suggestions now come only from locally recorded regular browsing history, show at most five matches after a short typing debounce, make no network suggestion request, and stay disabled in Incognito.
- Speed Dial tiles now show only the saved title/nickname instead of exposing the website address/host.
- When a page is added to Bookmarks/Speed Dial, the user can keep the suggested page title or choose a nickname before saving.
- Modernizes QuietShield's primary Home, Apps, Activity, Settings, Quick Access, search, Family, Child, onboarding, guide, Mobile Data Watch, and Private Browser surfaces with clear icons and restrained emojis.
- Keeps the existing lightweight View-based UI and adds no animated assets, bitmap icon packs, background timers, or third-party UI framework.
- Adds consistent visual cues for protection, apps, settings, Internet Rules, Mobile Data Watch, backup, Family, browser, updates, support, and diagnostics.
- Improves the Private Browser Speed Dial home and browser menu so browser actions are easier to distinguish at a glance.
- Carries forward the 2.7.5 buyer UX, Internet Rules, scoped search, Quick Access, backup/restore, Mobile Data Watch notification, VPN recovery, restore-safety, Parent warning, and fullscreen Fit/pinch fixes.

## 2.7.5 — Code301

**QuietShield 2.7.5 Code 301 Final**

- How QuietShield Works is expanded into a complete buyer and owner guide covering protection, permissions, Internet Rules, browser, Family, backup, notifications, reliability, updates, and important limits.
- Natural-language rules is renamed in the user interface to Internet Rules, and first-time setup adds Block all kinds of ads as the default Internet Rule when no equivalent rule already exists.
- Internet Rules and Mobile Data Watch are included in the curated default Quick Access; the editor uses icon controls and removes Battery reliability, Pause/resume protection, Quick Settings, and Secure websites from selectable shortcuts.
- Quick Access adds Internet Rules, Compatibility Exclusions, Mobile Data Watch, and Allowlist and Blocklist; Private Browser is presented as its own browser button rather than an ordinary settings row.
- Long-pressing a Private Browser Speed Dial now offers Edit title / nickname or Delete, with a separate delete confirmation.
- Home, Apps, and Settings now use inline search boxes. Home searches all role-available features, while Apps and Settings stay scoped to their section; Activity has no search box.
- Search matches names, keywords, and phrases, including Battery -> Battery reliability.
- Advanced Settings is reorganized under Connections & Data, Internet Rules & Lists, Privacy & Compatibility, Setup & Reliability, Backup & Recovery, and Family & Access.
- Mobile Data Watch has a dedicated notification-channel control so high-cellular-use summaries can be disabled without turning off the required VPN protection notification.
- Backup format 5 includes portable settings, Internet Rules, app policies, protection-list settings, browser bookmarks/Speed Dials, and Quick Access order while keeping runtime/device state excluded.
- Carries forward settings-restore crash repair, Android 16 VPN recovery hardening, Parent warning repair, and fullscreen Fit/pinch behavior.

## 2.7.4 — Code300

**QuietShield 2.7.4 Code 300 Final**

- Adds a comprehensive How QuietShield Works buyer/user guide covering protection, connections, Internet Rules, Private Browser, Family, backup, notifications, battery, updates, and limitations.
- Renames Natural-language rules to Internet Rules in user-facing UI and adds Block all kinds of ads as the first-setup default Internet Rule.
- Reworks Quick Access defaults and editor: Internet Rules is included by default, requested advanced shortcuts are available, removed shortcuts are no longer selectable, and reorder/remove controls use icons.
- Private Browser Speed Dials now support long-press rename/nickname and confirmed deletion.
- Home/Apps/Settings now use inline keyword search; Home is global, Apps/Settings are scoped, Activity has no search, and Battery finds Battery reliability.
- Settings advanced tools are grouped into Connections & Data, Internet Rules & Lists, Privacy & Compatibility, Setup & Reliability, Backup & Recovery, and Family & Access.
- Backup and Restore now includes Internet Rules, Private Browser bookmarks/Speed Dials, Quick Access order, app policies, protection-list sources, and portable settings.
- Adds a dedicated Android channel-settings screen so Mobile Data Watch summary notifications can be disabled without disabling the required VPN protection notification.
- Carries forward the settings-restore crash repair and legacy Int/Long preference recovery before normal startup reads.
- Keeps backup/restore limited to portable user-facing settings; runtime, migration, crash-loop, and device-local state remain excluded.
- Carries forward Android 16 VPN manager establish-recovery hardening.
- Carries forward the Parent stale needs_attention false-positive repair.
- Carries forward fullscreen Fit-by-default with pinch-out Fill and pinch-in Fit.
- Uses a fresh no-configuration-cache test/lint/build with strict APK identity and permanent signer verification.

## 2.7.3 — Code299

**QuietShield 2.7.3 Code 299 Final**

- Repairs legacy settings backups that restored Long preferences such as pause/runtime counters as Int values and could cause a persistent startup ClassCastException.
- Settings restore now imports only portable user settings instead of raw runtime, migration, crash-loop, and device-local state.
- Code299 repairs already-corrupted numeric preference types before normal AppPrefs startup reads and installs crash capture earlier in Application startup.
- Carries forward the Android 16 VPN manager establish-recovery hardening from Code298.
- Carries forward the Parent false-positive Child Protection warning repair.
- Carries forward fullscreen video Fit-by-default behavior with restored pinch-out Fill and pinch-in Fit gestures.
- Keeps the selected fullscreen Fit/Fill mode across orientation and layout refreshes.
- Uses a fresh no-configuration-cache verification build and strict source, Gradle metadata, APK manifest, and signer gates before publication.

## 2.7.2 — Code298

**QuietShield 2.7.2 Code 298 Final**

- YouTube and other HTML5 fullscreen video now start in Fit mode, showing the complete picture instead of forcing center-crop Fill.
- Restores two-finger fullscreen video gestures: pinch outward selects Fill, while pinch inward returns to Fit.
- The selected Fit/Fill mode is preserved across fullscreen layout and orientation refreshes instead of being forced back to crop-to-fill.
- Adds a narrow Android VPN manager classifier for IllegalStateException failures thrown from IVpnManager.establishVpn and VpnService.Builder.establish.
- Adds bounded fallback retries for that exact Android framework failure even when the older retry classifier does not recognize the stack shape.
- When automatic recovery is still available, transient Android VPN-manager failures are kept in the protection timeline instead of being placed in the pending crash/email store.
- If repeated recovery is exhausted, the failure is still recorded and protection is stopped so the owner receives an actionable diagnostic instead of an endless restart loop.
- Retains the 2.7.1 Parent false-positive warning repair, same-device Child recovery, role-aware Search QuietShield, faster Family sync, temporary access, and Code294 stability hardening.

## 2.7.1 — Code297

**QuietShield 2.7.1 Code 297 Final**

- Fixes a Parent false-positive red Child Protection Warning when a stale needs_attention status belongs to an older policy and the child has already applied a newer policy version.
- A genuine needs_attention status still remains red when it matches the currently assigned policy version exactly.
- Parent Family device cards now show readable Protection, VPN, Child Safety, Family role, and VPN permission lines instead of raw internal protection tokens.
- Applied policy cards show the effective applied version without exposing contradictory stale assigned/applied bookkeeping during a healthy state.
- Retains Family recovery, Search QuietShield, temporary access, requests, faster sync, and Code294 stability hardening.

## 2.7 — Code296

**QuietShield 2.7 Code 296 Final**

- Search QuietShield is available for Administrator, Parent, and Managed Child screens, with results filtered to the active role.
- Parents receive a red warning when a Managed Child reports protection trouble or stops checking in long enough that QuietShield may have been removed, force-stopped, restricted, offline, or powered off.
- Parents can safely re-register a missing child; the Family server reuses the previous registration when the same stable device fingerprint returns.
- Managed Child policy sync is faster and Parent cards clearly show presence and policy-delivery state.
- Parents can grant 15, 30, or 60 minutes of temporary access; children can request more time and see a safe explanation of why access is blocked.

## 2.6.9 — Code295

**QuietShield 2.6.9 Code 295 Beta 1**

- Parents now get a red child-protection warning when a Managed Child reports a protection problem or stops checking in long enough that QuietShield may have been removed, force-stopped, restricted, offline, or powered off.
- A missing child can be released and re-registered safely; the existing R1.5.3 Family server matches the same stable device fingerprint to the previous Sheet registration and keeps permanent revocation reserved for real security/admin revocation.
- Managed Child policy sync is faster while protection is running, and Parent cards show Online, Delayed, Missing, Applied, Pending, or Needs attention states.
- Parents can grant 15/30/60 minutes of temporary internet access; children can request more time and see a clear Why is this blocked explanation while explicit blocks and Child Safety remain protected.
- Adds a role-aware Search QuietShield screen for Administrator, Parent, and Managed Child devices so users can find settings and features by name or by natural keywords without exposing Parent/Admin controls to a child.

## 2.6.8 — Code294

**QuietShield 2.6.8 Code 294 Final**

- Fixed a dialog/window detach race that could produce a WindowManager IllegalArgumentException while an Activity was closing.
- Parent Family Dashboard refreshes are now coalesced and lifecycle-stale refresh results are discarded instead of rebuilding the screen repeatedly.
- Private Browser history renders at most 100 matching cards per pass, preventing very large saved histories from blocking the Android main thread.
- A privacy-safe UI stall watchdog now records the main-thread stack when the app stops responding for several seconds, while Natural-Language Rules, automatic child sync, reusable Family release, and protection behavior are retained.

## 2.6.7 — Code293

**QuietShield 2.6.7 Code 293 Final**

- Releasing a Family device now frees its seat without permanently revoking that phone or tablet; the same device may be enrolled again later when a Family seat is available.
- Family limits remain 2 Parent devices and 5 Child/Family-member devices, and only active devices consume those seats.
- Parent Child-device settings now use a clearer Natural-Language Rules editor with Interpret rules and Confirm rules before sending.
- Policy delivery clearly distinguishes waiting for automatic child sync from Applied by child; the child manual action is only an immediate update check.
- A released device still clears its old Family/Managed Child state on its next successful QuietShield server contact before returning to activation.
- True revoked status remains reserved for explicit security/admin denial. Reliable Parent-to-child synchronization, short pairing, Family Dashboard, Private Browser, App Connection Lock, Child Safety, and VPN resilience are retained.

## 2.6.6 — Code292

**QuietShield 2.6.6 Code 292 Final**

- Parent-to-child settings now converge reliably: policy sync runs on child app start/resume, Android boot/package replacement, manual Sync with parent, and the existing 15-minute Managed Child schedule.
- Heartbeat is best-effort and no longer blocks downloading or applying a valid Parent policy; concurrent sync requests join the active sync result instead of being dropped.
- Same-version pending child policies are retried and missing server acknowledgements are repaired automatically.
- Parents can manage each child's schedule with natural-language rules such as 'No YouTube after 9 PM on school nights'.
- Parent PIN is a Managed Child-only protection feature. Family Parent and Administrator devices do not expose or enforce a local Parent PIN.
- Each child's settings can provision or replace that child's protected PIN verifier without installing the PIN as a local lock on the Parent/Admin device.
- Admin Sandbox Family Dashboard, short QR/manual pairing, adaptive tablet GUI, Private Browser tablet dialog repair, VPN resilience, App Connection Lock, and Child Safety are retained.
- Fixes the Code291 unit-test compile regression by updating ChildDashboardPolicyTest for naturalRuleCount and the new schedule labels.
- Parent PIN is now a Managed Child-only protection feature: Family Parent and Administrator devices no longer expose or enforce a local Parent PIN.
- Each child's settings can provision or replace that child's Parent PIN verifier without installing the PIN on the Parent/Admin device.
- Parent policy sync is independent of heartbeat success; a heartbeat failure can no longer block downloading and applying child settings.
- Concurrent child sync requests now join the active sync and receive its final result instead of being dropped as already running.
- Managed Child policy sync now runs immediately after Android boot in addition to app start/resume, manual sync, and the existing 15-minute child schedule.
- Managed Child sync now runs immediately when Child Home opens and the manual Sync with parent action fetches and applies the assigned policy instead of sending only a heartbeat.
- A pending same-version policy is re-applied, and a lost server acknowledgement is repaired without requiring the parent to resave the policy.
- Managed Child devices check for policy changes every 15 minutes while family-parent heartbeats stay at the lower six-hour cadence.
- Child settings replace manual bedtime controls with up to 20 natural-language parent rules; scheduled rules are interpreted locally on the child using the child device app catalog.
- Natural-language rules now support all-app schedules such as Block all apps from 9 PM to 6 AM on weekdays.
- Saving child settings provisions the Parent PIN verifier to that child; Managed Child devices no longer create or remove their own separate Parent PIN.
- Parent PIN sync uses a salted PBKDF2-HMAC-SHA256 verifier; the plaintext PIN is not placed in the child policy.

## 2.6.5-beta1 — Code291

**QuietShield 2.6.5 Beta 1**

- Fixes the Code291 unit-test compile regression by updating ChildDashboardPolicyTest for naturalRuleCount and the new schedule labels.
- Parent PIN is now a Managed Child-only protection feature: Family Parent and Administrator devices no longer expose or enforce a local Parent PIN.
- Each child's settings can provision or replace that child's Parent PIN verifier without installing the PIN on the Parent/Admin device.
- Parent policy sync is independent of heartbeat success; a heartbeat failure can no longer block downloading and applying child settings.
- Concurrent child sync requests now join the active sync and receive its final result instead of being dropped as already running.
- Managed Child policy sync now runs immediately after Android boot in addition to app start/resume, manual sync, and the existing 15-minute child schedule.
- Managed Child sync now runs immediately when Child Home opens and the manual Sync with parent action fetches and applies the assigned policy instead of sending only a heartbeat.
- A pending same-version policy is re-applied, and a lost server acknowledgement is repaired without requiring the parent to resave the policy.
- Managed Child devices check for policy changes every 15 minutes while family-parent heartbeats stay at the lower six-hour cadence.
- Child settings replace manual bedtime controls with up to 20 natural-language parent rules; scheduled rules are interpreted locally on the child using the child device app catalog.
- Natural-language rules now support all-app schedules such as Block all apps from 9 PM to 6 AM on weekdays.
- Saving child settings provisions the Parent PIN verifier to that child; Managed Child devices no longer create or remove their own separate Parent PIN.
- Parent PIN sync uses a salted PBKDF2-HMAC-SHA256 verifier; the plaintext PIN is not placed in the child policy.

## 2.6.4 — Code290

**QuietShield 2.6.4 Code 290 Final**

- Private Browser close/Incognito dialogs now use a QuietShield-styled responsive card: sensible tablet width, readable cleanup choices, full-width primary action, and compact secondary actions without the gray default Android dialog.
- Fixes Child device settings on the Administrator phone: Admin Sandbox Family children now load/save through administrator-only sandbox policy APIs instead of incorrectly requiring the Family Parent SecureFamilyLinkStore.
- Fixes the activation QR compile regression by persisting Admin Sandbox Family context only in the Administrator InventoryKey path; normal Family-key pairing continues to use the String license key without invalid keyHash access.
- Fixes the wide-tablet dashboard compile regression by importing the Android Gravity API used by the compact navigation rail and two-column layout.
- Administrator Parent testing detects the Admin Sandbox Family containing enrolled child phones/tablets and shows them in Family Dashboard without consuming a production Parent slot.
- Managed Child enrollment retains the short five-minute single-use QR plus manual pairing-code fallback and routes a successfully paired child phone/tablet directly to Child Home.
- Wide tablets use a compact top-aligned navigation rail, a two-column Protection/Quick Access Home, and a two-column Settings/Family-Setup layout.
- Uses Code 290 so devices on Code 289 can detect QuietShield 2.6.4 Final as a genuine newer GitHub update.
- Administrator Parent testing now opens the actual Admin Sandbox Family used for child enrollment, so linked child phones/tablets appear in Family Dashboard without converting the Admin phone into a Family Parent.
- After successful Managed Child pairing, the child phone/tablet immediately opens Child Home instead of returning to an already-open full dashboard.
- Wide tablet Home and Settings use the available width beside a compact top-aligned navigation rail, including two-column Home and Settings layouts in landscape.
- Managed Child pairing is device-agnostic: the child may use an Android phone or tablet, with the same QR scan and manual pairing-code fallback.
- Parent/Child enrollment now uses a short five-minute one-time pairing code with a much simpler high-contrast QR; child tablets can enter the same code manually when their camera cannot scan the QR.
- Parent Command Center child enrollment no longer asks an Administrator to type a customer key: Administrators select/create only Admin Sandbox Family inventory, while real Family Parents automatically use their saved Family entitlement.
- Final publisher now derives its verified build-report filename from the release versionCode instead of using a stale hard-coded Code 288 filename.
- Parent Command Center now appears only on Administrator or Parent devices. Managed-child and regular-family devices do not show the parent-management entry.
- Final uses versionCode 289 so devices running the Code 288 GUI Beta can detect 2.6.3 Final as a genuine newer GitHub update.
- Parent Command Center is now directly visible as the first Family & Safety action so an administrator/parent can open child pairing, Family Overview, requests and alerts, and child-device setup without hunting through settings.
- Fixed bottom navigation on phones and an adaptive side rail on tablets keep Home, Apps, Activity, and Settings reachable without scrolling away.
- Simple Settings uses clearer descriptive switch rows, while Quick Access preserves user ordering with Add, Remove, Up, Down, and Reset controls.
- Private Browser keeps Back, Forward, and the address bar at the top, with Home, Bookmarks, Tabs, and Menu fixed at the bottom; secondary actions use grouped bottom sheets.
- Parent Command Center and Child Home use lightweight adaptive two-pane layouts on tablets and wide screens while remaining stacked and readable on phones.
- Universal supported HTML5 video seeking retains exact +/-10-second direct and cross-origin frame paths, with native compatibility fallbacks.
- Android VPN startup resilience, notification restoration, boot recovery, Child Safety, family policies, App Connection Lock, and the Code 287 RAM/battery efficiency work remain fully enabled.
- The GUI redesign adds no third-party showcase UI framework, Compose migration, continuous animation, blur engine, analytics SDK, UI polling service, or new background worker.

## 2.6.3 — Code289

**QuietShield 2.6.3 Code 289 Final**

- Administrator Parent testing now opens the actual Admin Sandbox Family used for child enrollment, so linked child phones/tablets appear in Family Dashboard without converting the Admin phone into a Family Parent.
- After successful Managed Child pairing, the child phone/tablet immediately opens Child Home instead of returning to an already-open full dashboard.
- Wide tablet Home and Settings use the available width beside a compact top-aligned navigation rail, including two-column Home and Settings layouts in landscape.
- Managed Child pairing is device-agnostic: the child may use an Android phone or tablet, with the same QR scan and manual pairing-code fallback.
- Parent/Child enrollment now uses a short five-minute one-time pairing code with a much simpler high-contrast QR; child tablets can enter the same code manually when their camera cannot scan the QR.
- Parent Command Center child enrollment no longer asks an Administrator to type a customer key: Administrators select/create only Admin Sandbox Family inventory, while real Family Parents automatically use their saved Family entitlement.
- Final publisher now derives its verified build-report filename from the release versionCode instead of using a stale hard-coded Code 288 filename.
- Parent Command Center now appears only on Administrator or Parent devices. Managed-child and regular-family devices do not show the parent-management entry.
- Final uses versionCode 289 so devices running the Code 288 GUI Beta can detect 2.6.3 Final as a genuine newer GitHub update.
- Parent Command Center is now directly visible as the first Family & Safety action so an administrator/parent can open child pairing, Family Overview, requests and alerts, and child-device setup without hunting through settings.
- Fixed bottom navigation on phones and an adaptive side rail on tablets keep Home, Apps, Activity, and Settings reachable without scrolling away.
- Simple Settings uses clearer descriptive switch rows, while Quick Access preserves user ordering with Add, Remove, Up, Down, and Reset controls.
- Private Browser keeps Back, Forward, and the address bar at the top, with Home, Bookmarks, Tabs, and Menu fixed at the bottom; secondary actions use grouped bottom sheets.
- Parent Command Center and Child Home use lightweight adaptive two-pane layouts on tablets and wide screens while remaining stacked and readable on phones.
- Universal supported HTML5 video seeking retains exact +/-10-second direct and cross-origin frame paths, with native compatibility fallbacks.
- Android VPN startup resilience, notification restoration, boot recovery, Child Safety, family policies, App Connection Lock, and the Code 287 RAM/battery efficiency work remain fully enabled.
- The GUI redesign adds no third-party showcase UI framework, Compose migration, continuous animation, blur engine, analytics SDK, UI polling service, or new background worker.

## 2.6.3 — Code288

**QuietShield 2.6.3 Code 288 Final**

- Parent Command Center is now directly visible as the first Family & Safety action so an administrator/parent can open child pairing, Family Overview, requests and alerts, and child-device setup without hunting through settings.
- Fixed bottom navigation on phones and an adaptive side rail on tablets keep Home, Apps, Activity, and Settings reachable without scrolling away.
- Simple Settings uses clearer descriptive switch rows, while Quick Access preserves user ordering with Add, Remove, Up, Down, and Reset controls.
- Private Browser keeps Back, Forward, and the address bar at the top, with Home, Bookmarks, Tabs, and Menu fixed at the bottom; secondary actions use grouped bottom sheets.
- Parent Command Center and Child Home use lightweight adaptive two-pane layouts on tablets and wide screens while remaining stacked and readable on phones.
- Universal supported HTML5 video seeking retains exact +/-10-second direct and cross-origin frame paths, with native compatibility fallbacks.
- Android VPN startup resilience, notification restoration, boot recovery, Child Safety, family policies, App Connection Lock, and the Code 287 RAM/battery efficiency work remain fully enabled.
- The GUI redesign adds no third-party showcase UI framework, Compose migration, continuous animation, blur engine, analytics SDK, UI polling service, or new background worker.

## 2.6.2 — Code287

**QuietShield 2.6.2 Code 287 Final**

- Lower unnecessary background CPU and battery work while VPN filtering, Child Safety, family rules, App Connection Lock, notification recovery, boot recovery, and protection remain fully functional.
- Modern minimal Control Center with uniform action rows, editable Quick Access, blue App Updates only when an update is available, and blue App Connection Lock only while Block all user apps is active.
- Parent Command Center, Child Home, access/license screens, and tablet layouts use clearer plain-language task-based controls.
- Private Browser improves inactive WebView memory handling, fullscreen efficiency, adaptive media wake checks, session behavior, and universal exact 10-second seek across supported direct and cross-origin HTML5 video frames.
- Android VPN startup distinguishes permission loss from crashes and adds bounded recovery for transient Android VPN-manager RemoteException and DeadObjectException failures.
- Final GitHub release uses the permanent QuietShield signing certificate and keeps the Google Play AAB and R8 mapping private.

## 2.6.1 — Code286

**QuietShield 2.6.1 Code 286 Beta 5**

- Fullscreen double-tap rewind/forward now has an exact cross-frame HTML5 seek path for videos embedded in cross-origin iframes, not only YouTube or same-origin players.
- The cross-frame bridge is event-only: no recurring timer or polling loop is added. It probes frames only when the user performs a seek gesture.
- Only the best active/fullscreen video frame is selected before seeking, avoiding simultaneous seeking of background or ad videos.
- Older WebView providers keep the existing direct HTML5 seek and native J/L, arrow, and media-key fallbacks.
- The fullscreen controller now allows enough time for the frame probe and exact seek before invoking native fallbacks.
- All Beta 1 through Beta 4 performance, RAM, battery, GUI, Quick Access, family, VPN resilience, notification, boot, and protection changes are retained.

## 2.6.0 — Code285

**QuietShield 2.6.0 Code 285 Final R1.6 Landscape Entry Repair**

- With Android auto-rotate enabled, tapping a website fullscreen button now rotates QuietShield into sensor landscape even when the phone is held upright.
- With auto-rotate disabled, fullscreen stays locked to a landscape direction.
- Edge-to-edge video cover is reapplied after the orientation change so the video fills the landscape display.
- Universal HTML5, iframe, shadow-root, SurfaceView, and TextureView cover paths remain included.
- The active protection notification recovery, Parent Command Center, and QuietShield Child Home remain included.

## 2.5.9 — Code284

**QuietShield 2.5.9 Code 284 Beta 1**

- Ten-second fullscreen rewind and forward now use exact HTML5 seeking across the page, same-origin frames, open shadow roots, and active fullscreen video, with safe native-player key fallbacks when needed.
- Fullscreen video follows Android's system auto-rotate setting and reacts when the setting changes while video is open.
- When system auto-rotate is enabled, playing HTML5 video can request fullscreen after landscape rotation where the website permits it.
- Normal Private Browser history is stored locally for 62 days with Today, 31 days, and 2 months filters, search, open, and delete controls.
- Incognito history is never recorded, and persistent history is removed when browsing-history deletion is selected.

## 2.5.8 — Code283

**QuietShield 2.5.8 Code 283 Final R1**

- Mobile Data Watch now highlights the actual selected Today, 7 days, or 31 days period and keeps that selection across recreation.
- Mobile Data Watch and Aggressive App Watch notify at most once per local calendar day.
- Mobile Data Watch measures cellular data only, excludes Wi-Fi, and starts from a fresh activation baseline.
- Private Browser uses resilient YouTube Skip Ad detection with repeated click attempts and continuous acceleration fallback.
- Fullscreen video double-tap seeking is placed on the left and right sides for ten-second rewind and forward.
- Code 281 schedules, reconnect behavior, App Connection Lock, Private Browser state, Incognito isolation, licensing, and permanent signing identity remain preserved.
- At-most-one notification per day for Mobile Data Watch
- At-most-one notification per day for Aggressive App Watch
- No same-day notification reposts
- Cellular-only TYPE_MOBILE Watch statistics
- First-activation data baseline
- High-use findings only
- YouTube Skip Ad enabled-state observer
- Approved-host and in-player validation
- Left-side rewind 10 seconds
- Right-side forward 10 seconds
- Website controls remain clickable
- Code 281 regression baselines retained
- This is a manually installed Beta. Test cellular/Wi-Fi transitions, local-day rollover, notification frequency, YouTube skippable ads, fullscreen settings, captions, timeline, brightness, volume, Lock, regular logins, and Incognito before any Final publication.

## 2.5.7 — Code282

**QuietShield 2.5.7 Code 282 Beta 1**

- Mobile Data Watch and Aggressive App Watch no longer create repeated ordinary alerts. Each Watch may notify at most once per local calendar day; later same-day findings are recorded without reposting.
- Mobile Data Watch queries Android TYPE_MOBILE statistics only. Wi-Fi is excluded from its totals, findings, history, and notifications.
- A first-activation baseline prevents cellular traffic from before Code 282 monitoring was enabled from becoming a new background warning.
- The Mobile Data Watch screen lists only apps with a meaningful high-cellular-use recommendation; ordinary traffic is not saved as Watch history.
- YouTube Auto-Skip now waits for an approved YouTube host, an active player ad state, and a visible enabled in-player Skip Ad control before clicking.
- The YouTube observer detects when a Skip Ad button changes from disabled to enabled, debounces repeat clicks, and never searches unrelated websites for generic Skip controls.
- Fullscreen double-tap seeking is restored only in the safe outer left and right zones. The second tap is consumed before the website can also seek, preventing an accidental twenty-second jump.
- The top, center, and lower website-control areas remain available to YouTube settings, captions, play/pause, quality, timeline, and fullscreen controls.
- Brightness and volume vertical gestures, fullscreen Lock, Incognito isolation, App Connection Lock schedules, pull-to-refresh, licensing, and permanent signer requirements are retained.
- YouTube ad handling now retries visible Skip Ad controls every 150 ms and always keeps the ad acceleration fallback active until the ad ends.
- R1.5 fixes the BrowserContentBlocker unit-test compile error while preserving R1.4 YouTube ad handling.
- R1.6 repairs the updater rollback validator without changing Code 282 runtime behavior.
- At-most-one notification per day for Mobile Data Watch
- At-most-one notification per day for Aggressive App Watch
- No same-day notification reposts
- Cellular-only TYPE_MOBILE Watch statistics
- First-activation data baseline
- High-use findings only
- YouTube Skip Ad enabled-state observer
- Approved-host and in-player validation
- Left-side rewind 10 seconds
- Right-side forward 10 seconds
- Website controls remain clickable
- Code 281 regression baselines retained
- This is a manually installed Beta. Test cellular/Wi-Fi transitions, local-day rollover, notification frequency, YouTube skippable ads, fullscreen settings, captions, timeline, brightness, volume, Lock, regular logins, and Incognito before any Final publication.

## 2.5.6 — Code281

**QuietShield 2.5.6 Code 281 Final**

- Scheduled App Connection Lock profiles with low-resource Android alarms
- Automatic profile reconnect and user notifications
- Mobile Data Watch for user, system, and Google app UIDs
- Discretion warnings and no automatic app blocking
- Profile editor keyboard focus and cursor repair
- Private Browser pull down to refresh
- Transparent strict-profile protection labels

## 2.5.5 — Code280

**QuietShield 2.5.5 Final**

- Private Browser privacy controls, premium tabs, preferred video quality, and YouTube fullscreen control priority.
- Preferred video quality now defaults to 1080p, with 720p fallback when exposed by the website player.
- Private Browser Home tabs use the QuietShield app icon and a single Home label.
- The regular-browser close prompt is restored for toolbar Close and the phone Back action from Home.
- Clear browsing data now can remove selected regular-browser data while preserving bookmarks and downloads.
- Incognito continues deleting only its isolated temporary profile while preserving regular browser logins.
- YouTube fullscreen bottom controls are fully website-owned; brightness and volume wait for a confirmed non-control touch.
- Customer activation pages use the generic Enter your key wording without exposing administrator, tester, or giveaway terminology.
- Picture-in-Picture remains removed from Private Browser.

## 2.5.3 — Code278

**QuietShield 2.5.3**

- Code 278 is intentionally higher than the manually installed Code 277 Beta so QuietShield can test detecting, downloading, verifying, and installing this Final through the in-app updater.
- Incognito uses a separate Android WebView profile when supported, so exiting Incognito no longer clears regular Private Browser cookies, logins, or website storage.
- Devices without safe WebView profile isolation refuse to start Incognito instead of using the old destructive shared-data fallback.
- Private Browser tabs show website favicons, compact titles, an active-tab surface, and immediate Home reset after closing a website tab.
- The phone Back button walks through website history, returns the active tab to Home, and then returns to the QuietShield dashboard.
- Long-press Back and Forward can show available history destinations, while unavailable navigation controls remain disabled.
- Visible Rewind 10 and Forward 10 controls replace fullscreen-wide double-tap seek zones and stay away from YouTube’s bottom-right settings area.
- QuietShield Home uses a guarded double-Back exit without intentionally stopping active VPN protection.
- Administrator authorization gates, renderer recovery, Smart Skip Beta, two-tab resource limits, App Connection Lock, and same-device activation restoration remain enabled.
- Picture-in-Picture remains removed while black-video behavior is unresolved.
- Higher Code 278 updater-test release
- Isolated Incognito WebView profile
- Regular browser login preservation
- Premium favicon tabs
- Phone Back history navigation
- Long-press Back and Forward history menu
- Disabled navigation-button states
- Visible ten-second video controls
- QuietShield Home double-Back guard
- Administrator-parent and child-device test readiness
- PiP remains removed
- Verified Direct GitHub update metadata
- Known Beta limitations: YouTube’s fullscreen settings cogwheel may remain unresponsive even when CC works, Smart Skip depends on community timestamps, fullscreen video behavior remains website and WebView dependent, and parent/child workflows require physical testing on the administrator phone and child tablet.

## 2.5.2 — Code277

**QuietShield 2.5.2 Beta 1**

- Incognito now uses a separate named WebView profile when the installed Android System WebView supports multi-profile isolation.
- Exiting Incognito deletes only the Incognito profile; regular Private Browser cookies, sign-in sessions, and website storage are not cleared.
- If profile isolation is unavailable, QuietShield refuses to start Incognito instead of using the previous destructive shared-data fallback.
- Private Browser tabs now show a compact favicon, one-line page title, active-tab border, and immediate Home reset when a tab is closed.
- The phone Back button now walks through the active website history, then returns the tab to Home, and only then returns to the QuietShield dashboard.
- Toolbar Back and Forward buttons are visibly disabled when no matching history exists.
- Long-pressing Back or Forward opens a compact list of up to five available history destinations and jumps directly to the selected entry.
- Fullscreen-wide double-tap seek zones are removed. Temporary visible Rewind 10 and Forward 10 buttons appear with QuietShield fullscreen controls and fade smoothly.
- The visible seek controls are disabled while fullscreen Lock is active and do not occupy YouTube's bottom-right settings area.
- The QuietShield Home dashboard now requires a second Back press within two seconds before the app is sent to the background; active VPN protection is not stopped.
- Code 277 is a manually installed Beta. Version 2.5.3 Code 278 is reserved for the later final release and Direct GitHub in-app update test.
- Administrator authorization gates, Smart Skip Beta, renderer recovery, two-tab resource limits, App Connection Lock, and removal of Private Browser PiP are retained.
- Isolated Incognito WebView profile
- Regular browser login preservation
- Crash-safe Incognito cleanup retry
- Premium favicon tabs
- Phone Back history navigation
- Long-press Back and Forward history menu
- Disabled navigation-button states
- Visible ten-second video controls
- No fullscreen-wide double-tap seek overlay
- Admin phone as parent test plan
- QuietShield Home double-Back exit guard
- Child-key tablet test plan
- Code 278 reserved for updater testing
- Private Browser video functions, Smart Skip, Incognito profile compatibility, and parent/child workflows remain Beta. Test regular logins before and after Incognito, browser history, explicit seek controls, administrator-parent behavior, and child-key restrictions before any repository publication.

## 2.5.1 — Code276

**QuietShield 2.5.1**

- Code 276 is intentionally higher than the manually installed Code 275 Beta so QuietShield can test detecting, downloading, verifying, and installing this Final through the in-app updater.
- Open Admin Test Lab remains hidden from trial and non-administrator users and is independently protected by an administrator check inside AdminTestLabActivity.
- A terminated WebView video renderer is now handled without allowing the dead renderer to take down the Private Browser activity; QuietShield rebuilds the affected tab and reloads its last known URL.
- The renderer-recovery path does not deliberately clear normal Private Browser cookies, bookmarks, or the saved two-tab session.
- Locked fullscreen continues to block website video touches and suggestions while preserving the visible QuietShield Unlock control and guarded two-step Back escape.
- Smart Skip remains Beta and can show community-timestamp buttons for supported openings, endings, recaps, sponsors, promotions, reminders, and previews.
- Picture-in-Picture remains removed from Private Browser while black-video behavior is unresolved.
- Incognito keeps its distinct dark-gray appearance and still deletes Incognito website data when the session ends.
- App Connection Lock, same-device activation restoration, VPN protection, signed update metadata, APK SHA-256 verification, and permanent signer continuity remain enabled.
- Higher Code 276 updater-test release
- Admin Test Lab authorization boundary
- WebView video renderer recovery
- Two-tab session preservation attempt
- Locked-fullscreen touch shield
- Smart Skip Beta retained
- PiP remains removed
- Dark-gray Incognito retained
- Verified Direct GitHub update
- Known Beta limitations: the YouTube fullscreen settings cogwheel may remain unresponsive even when CC works, Smart Skip depends on community timestamps, and one prolonged YouTube session reportedly terminated Private Browser without a captured app exception. Code 276 adds WebView renderer recovery, but the exact cause of that report was not conclusively reproduced.

## 2.5.0 — Code275

**QuietShield 2.5.0 Beta 1**

- Fullscreen Lock now blocks all website video touches except QuietShield's visible Unlock control, preventing suggestions, seeking, menus, and accidental playback changes while locked.
- The first Back press while locked keeps fullscreen open and shows a warning; Back again within two seconds safely unlocks and exits.
- YouTube now receives only the original cogwheel tap. The previous recovery click that could immediately close the settings menu has been removed.
- The lower website-control band is expanded so YouTube controls receive priority over QuietShield brightness, volume, and ten-second gestures.
- Smart Skip Beta can show Skip Opening, Ending, Recap, Sponsor, Promotion, Reminder, or Preview buttons when trusted community timestamps are available.
- Smart Skip performs no microphone recording, speech recognition, or continuous on-device AI analysis and remains off the playback path when no timestamps are found.
- Smart Skip uses one low-priority lookup worker, a small seven-day cache, and polls video time only while a known segment and fullscreen playback are active.
- The existing same-device activation flow is retained for regular, tester, child/family, and administrator keys so clearing app data or reinstalling with the same identity can reuse the existing device record.
- This Beta is version 2.5.0 Code 275. The later Final is reserved for a higher version, 2.5.1 Code 276, so the Direct GitHub in-app update can be tested from this Beta.
- Picture-in-Picture remains removed from Private Browser while black-video behavior is unresolved.
- Critical security hotfix: Open Admin Test Lab is hidden from trial and non-administrator users and independently administrator-gated at the activity boundary.
- Critical security repair: Open Admin Test Lab is hidden from trial/customer screens and the activity rejects non-administrator entry.
- True locked-video touch shield
- Suggestions disabled while locked
- YouTube original-tap-only cogwheel handling
- Expanded website control priority zone
- Smart Skip Beta timestamp buttons
- SponsorBlock and AniSkip lookup support
- Low-resource timestamp cache
- Same-device activation recovery test path
- Reserved higher Final version for in-app update testing
- PiP remains unavailable
- Private Browser video controls and Smart Skip remain Beta. Community timestamps may be unavailable or inaccurate. Test this Code 275 APK manually; the future Code 276 Final will be published through the verified Direct GitHub updater for the in-app update test.

## 2.4.9 — Code274

**QuietShield 2.4.9**

- Private Browser displays Home and Speed Dials immediately, then opens the filter engine and restores interrupted tabs after the first frame is queued.
- Brightness, volume, and ten-second seeking continue to use the Code 274 fullscreen gesture coordinator and protected website-control regions.
- Fullscreen Lock keeps website controls available and uses a guarded two-step Back action while locked.
- The remaining fullscreen Lock control fades smoothly after five seconds and returns after a screen touch.
- Picture-in-Picture has been temporarily removed from Private Browser because website fullscreen surfaces were still producing black video on supported devices.
- Incognito now changes the Private Browser toolbar, tabs, content area, Home page, and address field to a distinct dark-gray surface.
- Incognito cleanup still deletes its tabs, history, cookies, cache, form data, permissions, authentication information, and website storage when the session exits.
- The two-tab low-resource behavior, decision cache, App Connection Lock, VPN protection, and verified Direct GitHub updater remain unchanged.
- Faster visible Private Browser startup
- Distinct dark-gray Incognito appearance
- PiP temporarily removed from Private Browser
- Smooth fullscreen Lock fading
- Guarded two-step Back while locked
- Retained low-resource two-tab behavior
- Retained App Connection Lock and blocking protection
- Known limitation: YouTube's fullscreen settings cogwheel may still fail to open on some player layouts even when the nearby CC control works. Video gestures and fullscreen behavior remain website- and WebView-dependent.

## 2.4.8 — Code273

**QuietShield 2.4.8**

- Brightness, volume, and ten-second seeking now share one fullscreen coordinator that checks website controls before QuietShield claims a gesture.
- YouTube settings, captions, menus, sliders, seek controls, and other website-owned controls are protected by live hit testing.
- Incognito begins with clean website data and deletes its tabs, history, cookies, cache, form data, permissions, and website storage when the Incognito session exits.
- Interrupted Incognito sessions are marked for cleanup and purged before Private Browser restores a normal page.
- PiP is disabled for player surfaces known to be unsafe rather than deliberately opening a black PiP window.
- Fullscreen Lock disables QuietShield gestures only; PiP, Android Back, website controls, and fullscreen exit remain independently available.
- Lock and PiP controls fade smoothly after five seconds and return without intentionally consuming the website's first touch.
- The inactive second tab pauses media and receives a lower renderer priority to reduce unnecessary RAM, battery, and background activity.
- A bounded clean-decision cache avoids repeated browser blocking checks while never caching blocked decisions as clean.
- Fullscreen video, PiP, Incognito, and the new low-resource browser protections remain Beta and may vary by website, Android WebView, firmware, and device.
- Unified fullscreen gesture coordinator
- Live website-control hit testing
- Incognito clean-session toggle
- Crash-safe Incognito cleanup marker
- Conservative PiP capability gate
- Independent Lock and PiP state
- Smooth fullscreen control fading
- Low-resource two-tab behavior
- Bounded clean-decision cache
- Mixed-content and file-URL hardening
- Beta fullscreen, PiP, Incognito, and browser optimizations
- Final application release. Fullscreen video, PiP, Incognito, and the new low-resource browser protections remain Beta and will continue receiving compatibility and security improvements.

## 2.4.7 — Code272

**QuietShield 2.4.7**

- Private Browser supports up to two tabs and pauses inactive-tab media to reduce unnecessary RAM, battery, and bandwidth use.
- A confirmed Close Privacy Browser action closes the session and returns the next launch to Home/Speed Dials, while an unexpected closure can restore the previous session.
- Fullscreen video includes five-second QuietShield control fade, touch-to-reveal, brightness and volume gestures, screen-awake handling, and stronger exit recovery.
- App Connection Lock includes Blocked, Wi-Fi Only, Allowed on mobile data, and Allowed on both filters, plus warned manual system-app rules.
- Video Settings and video functions remain Beta. Picture-in-Picture, YouTube fullscreen settings, seeking, and gesture compatibility may vary by website, WebView, and device.
- Two Private Browser tabs
- Inactive-tab media suspension
- Clean-close Home/Speed Dial reset
- Unexpected-session restoration
- Fullscreen control fade and recovery
- Brightness and volume video gestures
- Expanded App Connection Lock filters
- Warned system-app connection rules
- Video Settings and video functions remain Beta
- Final app release. Video Settings and all video functions remain Beta and will continue receiving compatibility repairs.

## 2.4.6 — Code271

**QuietShield 2.4.6**

- Private Browser now opens to an AMOLED bookmark-backed Speed Dial and retains the last active page when QuietShield is minimized.
- Fullscreen double-tap seeking is limited to protected upper-left and upper-right zones, with a subtle one-second 10-second indicator.
- The lower player-control area remains website-owned so YouTube settings, captions, seek bar, and fullscreen controls stay clickable.
- The address bar now uses a neutral dark background with direct Share, Copy, Paste, Go, Edit, and Voice actions.
- Block all user apps still excludes system apps by default, while optional advanced system-app restrictions require explicit warnings.
- The bounded Android VPN establishment recovery and verified GitHub update channel remain enabled.
- AMOLED Private Browser Speed Dial
- Local bookmark favicons
- Last-page restore after minimizing
- Safer 10-second fullscreen seeking
- YouTube fullscreen control protection
- Direct address-bar actions
- Advanced system-app restriction warnings
- GitHub update channel retained
- Android 14 VPN startup reliability
- Direct GitHub edition. The separate Google Play edition will remove external APK updating only after the Organization account is approved.

## 2.4.5 — Code269

**QuietShield 2.4.5**

- Submitting an address now clears focus, hides the keyboard, and returns focus to the webpage.
- The compact toolbar keeps Back, Forward, Address, Bookmarks, and Menu on one clean row. Reload, mobile or desktop view, Shields, site access, video actions, and browser preferences are in the menu.
- QuietShield no longer places a screen-sized gesture detector over fullscreen video, so YouTube settings, captions, seek bar, and fullscreen controls receive touches directly.
- The fullscreen lock prevents Back and website fullscreen-exit requests without blocking normal player controls.
- Picture-in-Picture isolates the active HTML5 video and hides sibling page elements before Android PiP opens, then restores the exact page on return.
- PiP adds rewind 10 seconds, play or pause, forward 10 seconds, and subtitles when the website exposes captions.
- Android Back keeps Private Browser alive in the background whenever audio or video is playing.
- Compact premium browser toolbar
- Keyboard dismissal after navigation
- Direct YouTube fullscreen controls
- Video-only Picture-in-Picture
- PiP rewind, play, forward and subtitles
- Media-safe Back behavior
- Mobile and desktop site modes
- Local phone and tablet final candidate. Repository publication remains disabled until device testing passes.

## 2.4.5 — Code262

**QuietShield 2.4.5**

- Replaces the large fullscreen Lock label with a small movable lock control. Portrait and landscape positions are remembered so the control can be moved away from website buttons.
- Adds Float video through Android Picture-in-Picture from normal webpage playback or fullscreen playback while preserving the page and playback position.
- Repairs Fill and Fit so the video uses center cropping instead of magnifying the complete player and blurring its controls.
- Adds Auto Premium quality preferences: 1080p on Wi-Fi, 720p on mobile data, and controlled reduction when buffering or a slow connection is detected.
- Adds Video settings for quality mode, mobile and Wi-Fi preferences, higher-resolution preference, remembered Fit or Fill, Float video, and screen-awake behavior.
- Adds one-time unsafe-network warnings when the Private Browser detects a real sign-in form, password field, passkey flow, or authentication page.
- Adds privacy-preserving possible sign-in notifications outside the Private Browser using authentication-domain hints only. QuietShield does not read another app's screen or encrypted page contents.
- Adds App Connection Lock filters for All apps, Blocked, Wi-Fi only, Mobile data only, and Wi-Fi and mobile data. Search and staged policy changes remain available.
- Movable fullscreen lock
- Float video Picture-in-Picture
- Non-blurry Fill and Fit
- Auto Premium quality
- Secure Sign-In Guard
- App Connection Lock access filters
- Stable phone and tablet release. QuietShield Android TV remains a separate application.

## 2.4.5-beta1 — Code261

**QuietShield 2.4.5 Beta 1**

- Replaces the large Lock fullscreen label with a small movable lock control. Its portrait and landscape positions are remembered, and the control can be moved away from a website's own settings buttons.
- Adds Float video through Android Picture-in-Picture from normal webpage playback or fullscreen playback, while preserving the same page and playback position.
- Repairs Fill and Fit so the video element uses YouTube-style center cropping instead of magnifying the entire player and blurring its controls.
- Adds Auto Premium quality: 1080p is preferred on Wi-Fi, 720p on mobile data, and quality is reduced when buffering or a slow connection is detected. When neither 1080p nor 720p exists, the highest available permitted stream is requested.
- Adds a Video settings screen for quality mode, mobile and Wi-Fi preferences, higher-resolution preference, remembered Fit/Fill, Float video, and screen-awake behavior.
- Adds one-time unsafe-network warnings when the Private Browser detects a real sign-in form, password field, passkey flow, or authentication page.
- Adds privacy-preserving possible sign-in notifications outside the Private Browser by using DNS authentication-domain hints only. QuietShield does not read another app's screen, password fields, or encrypted page contents.
- Adds an App Connection Lock access filter for All apps, Blocked, Wi-Fi only, Mobile data only, and Wi-Fi and mobile data. It combines with search and reflects staged changes and the active strict profile immediately.
- Movable fullscreen lock
- Float video Picture-in-Picture
- Non-blurry Fill and Fit
- Auto Premium 1080p/720p preference
- Secure Sign-In Guard
- App Connection Lock access filter
- Beta only. Android TV, public update.json, and customer release publication are unchanged.

## 2.4.4 — Code260

**QuietShield 2.4.4**

- Adds a persistent Lock fullscreen control above Private Browser videos so it remains visible after YouTube or another HTML5 video enters fullscreen.
- While fullscreen is locked, the first Back press warns the user and a second Back press within two seconds exits.
- Pinch outward fills the fullscreen video; pinch inward returns it to normal fitted fullscreen.
- Fixes the fullscreen overlay order so Lock and gesture indicators remain above the video.
- Adds bounded recovery for transient Android VPN framework RemoteException failures during VpnService.Builder.establish().
- Retains compact notification statistics and Open, Turn Off, and Turn On actions.
- Retains App Connection Lock in Home Quick actions, direct App Updates on launch, and R1.4 readable Home statistics.
- Does not add background playback, downloads, stream extraction, VLC, Media3, or ExoPlayer.

## 2.4.4 — Code259

**QuietShield 2.4.4**

- Shows compact notification statistics such as Blocked 12.4K • Saved 1.26 GB so both values remain visible at a glance.
- Adds Turn Off beside Open in the active protection notification.
- Turn Off asks whether to turn protection off for 10 minutes, turn it off until manually enabled, or cancel.
- While protection is temporarily paused, the notification action changes to Turn On.
- A ten-minute pause automatically restores the active notification and protection state.
- Retains App Connection Lock in Home Quick actions.
- Retains direct App Updates on launch and the R1.4 readable Home protection statistics.
- Does not include discarded Code 255 fullscreen or Code 256 strict-trial changes.

## 2.4.4 — Code258

**QuietShield 2.4.4**

- Restores App Connection Lock to Home Quick actions beside Data usage.
- Protection level remains available in the More settings section instead of occupying the Quick action.
- When a newer verified QuietShield version is available, app launch opens App Updates directly.
- Retains startup update-check timeout, onboarding precedence, and redirect-loop prevention.
- Retains the R1.4 readable Blocked Today and Saved Data display.
- Retains existing VPN, Private Browser, bookmarks, Data Usage, licensing, family, and administrator behavior.
- Does not include discarded Code 255 fullscreen-comfort or Code 256 strict-trial changes.

## 2.4.4-beta3 — Code257

**QuietShield 2.4.4 Beta 3**

- When a newer verified QuietShield version is available, app launch opens App Updates instead of leaving the user on Home.
- A previously confirmed update opens immediately; otherwise QuietShield performs a fresh launch check.
- The startup check uses a temporary non-cancelable progress gate so Home cannot be used before the initial result.
- If the network check takes longer than eight seconds, Home becomes usable while the check continues.
- Returning from App Updates does not create a Back-button redirect loop.
- First-run onboarding and certificate setup still finish before automatic update routing begins.
- Retains the R1.4 readable Blocked Today and Saved Data display.
- Does not include discarded Code 255 fullscreen comfort or Code 256 strict-trial changes.

## 2.4.3 — Code254

**QuietShield 2.4.3 final**

- Improves Blocked Today and Saved Data readability while keeping the complete value and MB/GB/TB unit on one line.
- Adds fullscreen Private Browser brightness and media-volume gestures.
- Adds local Private Browser bookmarks without automatic browsing history.
- Adds monthly and daily Wi-Fi and Mobile Data reports with the top 10 apps first and remaining apps alphabetically.
- Adds QuietShield Private Browser to Data Usage using only browser-reported transfer bytes.
- Keeps Blocked Today and Saved Data on one compact line on Home and in the protection notification.
- Keeps the existing trial, legacy license keys, administrator licenses, three-device policy, and GitHub update delivery.

## 2.4.3-beta2 — Code253

**Private Browser fullscreen controls, bookmarks, and browser-only data usage**

- Keeps Blocked Today and Saved Data on one compact line on Home and in the protection notification, using a smaller auto-adjusting font.
- Adds fullscreen vertical swipe controls: left side adjusts this window's brightness and right side adjusts media volume.
- Adds local Private Browser bookmarks without creating automatic browsing history.
- Adds QuietShield Private Browser to Wi-Fi and Mobile Data reports using only transfer bytes reported by the Private Browser WebView.
- Keeps QuietShield VPN, DNS, update, activation, and family-control traffic excluded from the Private Browser data entry.
- Removes the restricted-app count from the protection notification while retaining Blocked Today and Saved Data.
- Does not add locked-screen YouTube playback, background-play bypasses, VLC, Media3, ExoPlayer, or external-player integration.

## 2.4.3-beta1 — Code252

**Accurate statistics, daily data logs, and a simpler home screen**

- Retains Saved Data on Home, notifications, diagnostics, and Activity using one conservative category-weighted calculation.
- Explains under How it works that blocked resource sizes are not directly downloadable or measurable after DNS blocking.
- Adds selectable daily Wi-Fi and Mobile Data logs while retaining monthly reports and two-month history.
- Lists the top 10 data-using apps first and every remaining app in alphabetical order.
- Simplifies Home to Today, Categories, Protection, and DNS, with advanced details behind Protection level.
- Adds Support, Pending errors, Quick Settings, and How it works to Quick actions.
- Uses friendly offline and update-service messages without exposing raw repository addresses.

## 2.4.2 — Code251

**Fullscreen video, monthly data usage, and website requests**

- Repairs YouTube and HTML5 fullscreen video inside QuietShield without bundling a separate media player.
- Renames Mobile Data Usage to Data usage and separates current-month Wi-Fi and mobile app rankings.
- Resets current Wi-Fi and mobile rankings at each local calendar month while retaining the current and previous month.
- Allows managed-child devices to request parent review of a blocked website without sending page contents or browsing history.
- Lets a linked parent allow once for 15 minutes, always allow, or deny a website request.

## 2.4.1-beta3 — Code249

**QuietShield 2.4.1 Beta 3**

- Contains ordinary website connection failures inside the affected local web-filter request instead of treating them as application crashes.
- Prevents activation transfer and release operations from overlapping or being queued by rapid repeated taps.
- Uses Nearby Wi-Fi Devices on Android 13 and newer without requesting unnecessary precise location access.
- Keeps the legacy Wi-Fi location-permission path only on Android 12L and older.
- Removes obsolete Code 248 universal-notification resources and generated root marker files.
- Adds a source audit and an optional non-destructive Git-index cleanup tool for generated backup and build files.
- Preserves Code 247 secure receipt-authenticated licensing and Code 248 Samsung-tablet scrolling and notification behavior.

## 2.4.1-beta2 — Code248

**QuietShield 2.4.1 Beta 2**

- Uses a transparent outline notification glyph only on Samsung tablets.
- Honor and other manufacturers retain the existing working notification icon.
- Keeps App Updates actions visible while long release notes scroll.
- Makes safe plain vertical screens adaptively scrollable.

## 2.4.1-beta1 — Code247

**Secure activation release and transfer**

- Beta Tester and regular Premium activations can release the current device using their server-signed receipt when the encrypted serial is unavailable.
- Current-device transfer QR creation can use the same signed-receipt recovery path.
- Family activations continue to prefer the encrypted family link secret when available.
- Administrator activations remain blocked from customer release and transfer tools.
- The server verifies the receipt signature, current device hash, license hash, license type, active license record, expiration, and active device seat.
- Local activation data is cleared only after the server confirms that the current seat was released.

## 2.4.0 — Code246

**QuietShield 2.4.0**

- Recommended compatibility exclusions can be adjusted and restored.
- Private Browser address controls support select-all, precise editing, copy, paste, and sharing.
- Private Browser ad and tracker cleanup is stronger and pauses while hidden.
- Mobile Data Usage provides 30 daily totals, saved history, top-app attribution, and real-time connection visuals.
- App Connection Lock and Mobile Data Usage are available from Home quick actions.
- QR camera failures show recovery actions instead of terminating QuietShield.
- Temporary website-server connection failures remain limited to the affected request.
- Samsung-safe updates, the working Allowlist, tablet notification icon, and centered launcher are preserved.

## 2.4.0-beta3 — Code244

**Camera, real-time mobile state, and web-filter recovery**

- QR scanning now handles CameraAccessException and camera-session failures without terminating QuietShield.
- The scanner offers Retry camera and a return-to-pasted-activation fallback instead of closing unexpectedly.
- Mobile-data buttons update immediately when Wi-Fi or cellular connectivity changes.
- Mobile Data Usage and App Connection Lock are now available from Home quick actions.
- Transient connection refusals and timeouts in the local web filter no longer escape the worker thread as app crashes.
- Working Allowlist, Private Browser, compatibility exclusions, VPN, licensing, and phone/tablet icon behavior are preserved.

## 2.4.0-beta2 — Code243

**Browser and mobile-data stability**

- Mobile-data reports are cached for six hours instead of querying Android whenever the screen resumes.
- Stored top-app totals and the last update time remain visible while Wi-Fi is active.
- A failed Samsung daily counter keeps its previous saved value when possible.
- Shared Android UIDs are explained instead of appearing as unexplained duplicate apps.
- The Privacy Browser pauses periodic cosmetic cleanup while its page is hidden.
- YouTube ad handling restores the original video speed and mute state after the ad surface disappears.
- The second address-bar tap places the cursor near the touched character.
- The working Allowlist, compatibility exclusions, VPN behavior, licensing, and icon resources are unchanged.

## 2.4.0-beta1 — Code242

**Compatibility, Private Browser, mobile data, and launcher update**

- Recommended compatibility exclusions may be turned off after a warning and restored individually or all at once.
- Secure website protection no longer shows Technical details.
- Private Browser adds stronger request blocking, page-lifetime cosmetic cleanup, YouTube-specific cleanup, and copy/paste/share address controls.
- A mobile-data-only 30-day report shows daily totals and the top ten apps when Android Usage Access is granted.
- The adaptive and legacy launcher artwork is centered, safely inset, and stripped of the detached corner artifact.

## 2.3.2 — Code241

**Tablet notification icon clarity**

- Samsung tablets and other sw600dp large-screen devices use a smaller notification shield with a transparent checkmark.
- The existing phone notification icon remains byte-for-byte unchanged.
- Protection, Allowlist, ad/tracker filtering, licensing, administrator authentication, and update behavior are unchanged.
- Existing notification builders continue using the dedicated QuietShield notification resource.

## 2.3.1 — Code240

**QuietShield 2.3.1 Final**

- The working Code 239 website Allowlist compatibility is retained.
- QuietShield no longer registers itself as the general handler for downloaded APK files.
- Verified in-app updates prefer Android or Samsung system package installer.
- File Safety recognizes a same-package, same-signature QuietShield APK as verified.
- A forged APK with only the QuietShield package name is not trusted.
- Phone and tablet upgrades preserve existing data and settings.

## 2.3.1-beta6 — Code239

**Underlying-network DNS compatibility for Allowlist**

- Allowlisted domains no longer use QuietShield encrypted DNS or its DNS cache.
- Approved sites resolve through the active Wi-Fi, mobile, or ethernet network DNS.
- The approved HTTPS destination continues using direct end-to-end TLS.
- Unrelated advertising, tracker, analytics, malware, phishing, and other hosts remain filtered.
- Allowed-request logs identify the resolver path when logging is enabled.

## 2.3.1-beta5 — Code238

**Audited website Allowlist compatibility**

- Custom website rules now clearly labels Allowlist and Blocklist.
- The rule fields accept normalized domains only and reject malformed or overbroad entries.
- An allowlisted destination bypasses DNS, natural-language, category, CNAME, risk-warning, redirect, proxy-path, and HTTPS certificate blocking.
- Allowlisted HTTPS destinations keep the browser's original end-to-end TLS connection.
- Unrelated advertising, tracker, analytics, malware, phishing, and other third-party hosts remain filtered.
- Admin Test Lab authenticates once at entry using biometric first and PIN fallback.
- A dedicated notification shield is enforced for phones and tablets.

## 2.3.1-beta4 — Code237

**Authoritative website allowlist repair**

- Allowed destinations now bypass the authoritative domain blocker before every protection category is evaluated.
- Only the allowed domain and its subdomains bypass; unrelated advertising and tracker domains remain blocked.
- Entering www.example.com also covers example.com and its other subdomains.
- Website-rule changes continue to refresh protection without requiring an app restart.
- The clear phone and tablet notification shield from Code 236 is retained.

## 2.3.1-beta3 — Code236

**Website access and notification icon beta**

- Allowed websites can open while QuietShield continues blocking separate advertising and tracker domains.
- Website fields accept lowercase letters, numbers, dots and hyphens only.
- Uppercase website letters are changed to lowercase; other symbols are rejected.
- Administrator accounts bypass the parent PIN for normal controls, including stopping protection.
- Admin Test Lab remains fingerprint-first, with PIN as the secondary option.
- Notifications now use a dedicated monochrome shield icon for consistent phone and tablet display.

## 2.3.1-beta1 — Code234

**Website rules and connection reliability beta**

- Custom website rules accept domains or full URLs and apply immediately.
- Saving unchanged website rules no longer requests authentication.
- Administrator devices can save ordinary local settings without a parent PIN.
- Admin Test Lab prioritizes fingerprint with PIN fallback.
- Apply protection changes no longer remains visually stuck on reconnecting.

## 2.3.0 — Code233

**Final closed-test build**

- Adds a dedicated 21-day Beta Tester activation button for personal QS-T21 codes.
- Limits each Beta Tester code to the server-defined one Android device.
- Stops expected VPN interface shutdowns and rebuilds from being reported as packet-reader errors.
- Keeps controlled recovery for genuine packet-reader failures while protection should remain active.
- Uses QuietShield License Server 1.2.3 with the administrator inventory fast path.
- Removes the external purchase button from the Google Play closed-test build.

## 2.3.0-rc2-r5 — Code232

**Administrator devices and session repair**

- Two private administrator keys now support three separately bound phones or tablets each, for six active administrator devices total.
- Admin Test Lab can repair an outdated or missing local admin binding, show all six admin-device seats, and release a selected remote seat.
- License inventory, permanent key generation, one-time activation QR, QR-only customer transfer, family controls, and immutable trials remain included.
- Emergency device-owner release remains available locally even when the license server cannot be reached.
- Apps Script POST networking now follows the ContentService redirect manually and displays precise HTTP, redirect, JSON, DNS, TLS, or timeout diagnostics.
- License Server v1.2.2 removes repeated runtime sheet-schema migration work that could cause protected administrator sessions to time out.

## 2.3.0-rc1 — Code231

**Admin Full-Test RC**

- Two server-generated, device-bound administrator keys; PIN/fingerprint Admin Test Lab; protected release and rebind.
- Server key inventory, customer key generation, QR activation, and QR-only occupied-seat transfer.
- Immutable per-device seven-day trial history, per-child names, remote policies, alerts, and role conversion.
- Managed Child device-owner provisioning, uninstall protection, app approval, and unknown-source controls.

## 2.2.0-beta1 — Code227

**Family Link and secure QR activation**

- Parent devices can create five-minute, single-use, server-signed activation QR codes.
- Another QuietShield phone can scan the QR and activate without typing or receiving the permanent key.
- Family child/member devices are linked to the same family through a signed family receipt and encrypted device-link secret.
- The parent dashboard shows linked devices, slot use, last contact, protection state, and recent malicious or restricted website attempts.
- Managed-child devices send a minimal heartbeat and security events; full page content, messages, passwords, screenshots, and full browsing history are not uploaded.
- DARK AMOLED, startup controls, Unsafe Wi-Fi repair, file/APK scanning, Aggressive App Watch, and previous protection fixes are retained.

## 2.1.2-beta1 — Code226

**QuietShield 2.1.2 Beta 1**

- The true-black theme is now named DARK AMOLED while Follow system, Dark, and Light remain available.
- Run QuietShield at system startup is now a visible toggle in both Simple and Advanced settings.
- Unsafe Wi-Fi Guard can temporarily trust the current connection when Android hides the Wi-Fi name.
- Back navigation now offers Apply and leave, Leave without applying, or Keep editing when protection changes are pending.
- File & APK Safety Scan checks selected files locally and blocks high-risk APK installation from the QuietShield scan flow.
- Aggressive App Watch combines risky app declarations, recent ad/threat connections, and optional usage access.
- System apps are displayed in red where advanced system-app controls are shown.
- Repairs the built-in malware protection source and automatically refreshes it when the compiled rules are missing.
- This beta does not yet include the future family backend, parent heartbeat, or QR enrollment server workflows.

## 2.1.1 — Code225

**QuietShield 2.1.1**

- Block all user apps now uses a strict local IPv4 and IPv6 firewall. Only apps selected in the active profile can connect.
- Strict App Connection Lock blocks direct-IP, TCP, UDP, QUIC, IPv4, and IPv6 traffic from blocked user apps.
- The midnight reset is isolated to daily counters and no longer restarts protection or clears App Connection Lock runtime state.
- Protection, Always-on VPN recovery, the active profile, and the encrypted license key are preserved across reboot.
- QuietShield now supports the final five server-signed license types and the 2-parent/5-member family role model.
- When strict Block all user apps mode is active, selected allowed apps use normal Android networking outside QuietShield's DNS filtering. Turn strict mode off to restore normal all-app DNS protection.

## 2.1.0-beta5 — Code224

**QuietShield 2.1.0 Beta 5**

- Block all user apps now uses a strict packet-routing firewall. Only apps checked in the active profile can use the internet.
- Strict mode blocks direct-IP, IPv4, IPv6, TCP, UDP, and QUIC traffic from blocked user apps while QuietShield is connected.
- Newly installed user apps are blocked automatically until they are added to the allowed-app profile.
- The misleading App connection issue popup is replaced with an accurate strict-mode status or DNS-level limitation notice.
- The midnight, reboot, Always-on VPN, encrypted-key, and profile recovery fixes from Beta 4 remain included.
- Strict mode prioritizes the app firewall. Allowed apps use normal Android networking outside QuietShield's DNS filtering while strict mode is active. Individual per-app restrictions remain DNS-level.

## 2.1.0-beta4 — Code223

**QuietShield 2.1.0 Beta 4**

- The midnight reset now changes daily counters only. It no longer restarts the VPN or clears the App Connection Lock runtime state.
- Startup protection now uses delayed, bounded recovery after boot and user unlock instead of racing Android Always-on VPN startup.
- The encrypted license key is no longer deleted when Android Keystore is temporarily unavailable during startup.
- App Connection Lock reloads the installed-app catalog and reapplies the saved profile after startup recovery.
- A privacy-safe dated timeline records midnight rollover, boot recovery, Always-on state, VPN lifecycle, license verification, and App Connection Lock application.
- This is a critical phone/tablet stability beta. Android TV is not modified. Daily rollover resets statistics only; profiles, rules, license state, filters, and protection preferences are preserved.

## 2.1.0-beta3 — Code222

**QuietShield 2.1.0 Beta 3**

- QuietShield now recognizes five server-signed key categories: administrator, 21-day tester, 2-parent/5-member family, 25-device giveaway, and regular 3-device Premium.
- Family setup supports two parent slots and five family-member slots. A family member may be managed child or regular Premium.
- One hundred unique 21-day tester keys and one hundred family keys can be imported securely through the private server registry.
- The tester period begins at first successful activation and the app verifies the key at every cold start and device boot.
- All earlier automatic updater, Wi-Fi, diagnostic, offline risk, protection-card, filter-health, and App Connection Lock beta features remain included.
- Bulk keys must be imported into the private Apps Script registry. Complete keys must never be embedded in the APK or published in the public release repository.

## 2.1.0-beta2 — Code221

**QuietShield 2.1.0 Beta 2**

- Family member setup now lets the parent choose Managed child or Regular Premium family member.
- Regular Premium family members consume a family-device slot but do not receive child-role restrictions or parent profiles.
- Managed child mode forces Child Safety on and role changes require parent authorization plus server confirmation.
- Cold-start, boot, and network-return license verification from the previous beta remain included.
- Automatic update detection, error-only text reports, Wi-Fi SSID repair, offline site-risk warnings, responsive protection details, and App Connection Lock DNS beta remain included.
- Family member activation and role changes require the accompanying Apps Script v1.0.8 server patch. QR enrollment, heartbeat, remote alerts, and uninstall indication remain server-dependent and are not represented as active.

## Unknown — Code220

**Live updates, safer Wi-Fi, and clearer protection**

- Every cold app start and device boot now verifies the saved license with the server; shared beta tester receipts display the fixed 21-day period and 25-device limit correctly.
- QuietShield can detect a newer verified release while running and show an update notification with its own icon.
- Start-after-restart recovery, cache-resistant update checks, and bounded background checks improve protection and update reliability.
- Unsafe Wi-Fi Guard can request the permissions needed for the real network name and will never trust an unknown SSID.
- Offline local website-risk warnings, trusted-site controls, and error-only .txt attachments add safer, privacy-conscious support.
- The protection card now uses readable sections for today, categories, engine, protection, DNS, and filter status.
- App Connection Lock returns as a DNS-level beta without excluding allowed apps from QuietShield protection.
- Controlled beta: server deployment is required before distributing the shared 25-device tester key. Direct-IP App Connection Lock traffic, signed remote filter deployment, and family enrollment remain subject to their disclosed limitations.

## Unknown — Code211

**Protection stability and update reliability**

- Fixed the secure-web proxy shutdown race that could produce a RejectedExecutionException while protection was restarting.
- Added Protection Effectiveness checks for the engine, all-app routing, packet reader, filter readiness, and recent traffic.
- Added privacy-safe reports for missed ads, trackers, phishing, broken pages, and possible false blocks.
- Natural-language rules now support up to 100 saved rules, with signed administrator diagnostics and stronger release hardening.
- App Connection Lock profiles remain saved while runtime enforcement stays temporarily paused to protect reliable all-app filtering.

## Unknown — Code208

**All-app routing repair**

- Normal protection now uses DNS-only routing for every non-excluded app and never creates a limited allowed-app VPN list.
- App Connection Lock profiles are preserved but temporarily suspended in this critical beta so they cannot disable ad and tracker protection in other apps.
- Something not working? now opens the real protection check, diagnostics, export, and protection-engine restart panel directly.
- The privacy-safe report now records the active routing mode and whether App Connection Lock was suspended.
- Before sharing this beta, confirm that Block Today rises above zero in more than one ad-supported app.

## Unknown — Code207

**Protection recovery update**

- QuietShield now performs a genuine protection-engine restart after an in-place update when protection was already enabled.
- Date, time-zone, and clock changes now use the established full VPN restart path.
- An enabled protection setting is recovered when the VPN service is unexpectedly missing.
- The What’s New window now scrolls correctly, keeps the Close button visible, and prevents large text from overlapping.
- Confirm that ads are blocked and Block Today increases before sharing this beta.

## Unknown — Code206

**Critical protection reliability update**

- A critical midnight rollover repair so daily counters can reset without leaving the VPN visible but no longer filtering.
- A protection-engine health guard that checks the VPN interface, DNS resolver, filters, cache, and packet-reader thread.
- Automatic controlled recovery that rebuilds the VPN tunnel without intentionally erasing the saved protection preference.
- A real Restart protection engine action under “App or website not working?”.
- The existing “Something not working?” row now opens the full protection check, privacy-safe diagnostics, export, and engine-restart panel.
- Privacy-safe Run protection check, Copy diagnostics, and Export diagnostic report actions.
- Trial and paid installations continue to use the same built-in App updates entry point.
- App-update access remains available to trial and paid installations of the same QuietShield Premium package.
- A professional one-time “What’s new” summary after an in-place update; it is not shown after a fresh installation.
- Beta security notice: keep this version in controlled testing until the midnight rollover, restart recovery, trial update, and 24-hour continuous-protection checks pass.
