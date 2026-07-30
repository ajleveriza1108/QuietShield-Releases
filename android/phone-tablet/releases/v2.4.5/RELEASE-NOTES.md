# QuietShield 2.4.5 — Final Code 269 R1.1

Stable Android phone and tablet release.

## Private Browser

- Compact premium browser toolbar with Back, Forward, Address, Bookmark, and Menu.
- Browser settings and secondary actions are consolidated in the menu.
- Mobile and Desktop website modes.
- Keyboard closes and webpage focus returns after URL submission.
- Bookmarks remain directly available from the toolbar.
- Silent background update checking.

## Video and fullscreen

- Website controls receive direct touches in fullscreen.
- YouTube settings, captions, seek bar, and fullscreen controls remain accessible.
- Movable Lock and Picture-in-Picture controls begin at the left-center.
- Fullscreen Lock protects against accidental Back navigation until unlocked.
- Normal fitted fullscreen is the default instead of blurry forced Fill.
- Picture-in-Picture waits for a detected, decoded HTML5 video frame.
- PiP actions include play or pause, rewind 10 seconds, and forward 10 seconds.
- Subtitle control is available where the website exposes usable HTML5 text tracks.
- Returning from PiP restores the browser page, toolbar, timers, and navigation.
- Back during active media keeps Private Browser alive in the background.

## Filtering and playback

- Normal YouTube media remains playable.
- YouTube advertising APIs and known ad surfaces remain filtered.
- The app avoids media-response cancellation that can create frozen or unskippable ads.
- Aggressive global seeking, repeating full-page cleanup, and forced 16x playback are not used.
- WebView hardware rendering and normal cache behavior are retained.

## Compatibility note

Website-specific fullscreen, captions, and Picture-in-Picture controls depend on
the player technology exposed by the website. Protected DRM, canvas-rendered,
or proprietary embedded players may not expose every control.

## Release information

- Package: `com.ajleveriza.quietshield`
- Version: `2.4.5`
- Version code: `269`
- Revision: `R1.1`
- Android phones and tablets.
- Android TV remains a separate application.
- The Play AAB, R8 mapping, keystore, licensing configuration, and administrator
  security material are not public.
