# OLaunch plan

A launcher for Android where nothing is locked to one look. It should run on almost any phone, including older ones, so it can be shared with friends and maybe released publicly.

## Principles

1. **Customizable by default.** A home screen "style" is saved data, not a fixed template. Every detail can be changed, and styles can be exported and shared.
2. **Wallpaper is a feature, not a backdrop.** Layers, blending, blur, tint and live preview, all non-destructive.
3. **Works on old phones.** Android 7.0 (API 24) and up. Newer-only effects may be optional extras, but never required.
4. **Private.** No network access and no analytics.

## First three styles

1. **Wallpaper Showcase.** Full-screen wallpaper, a thin dock, and an app list that slides up over a blurred wallpaper.
2. **Free Canvas.** Place, resize and rotate icons and widgets anywhere, with no grid.
3. **Dashboard.** Ready-made cards (clock, weather, calendar, music, suggested apps) on the same canvas.

A Dashboard is a Canvas with pre-arranged cards, and a Showcase is a Canvas with almost nothing on it, so the styles blend into each other.

## Wallpaper studio

- Stack images, colors and gradients, each with opacity and a blend mode (multiply, screen, overlay, darken, lighten, add).
- Effects: blur, dim, tint, grain and vignette, plus a "dim behind icons" option.
- The finished result is rendered once and cached, so scrolling stays smooth on weak hardware.
- Images come from the system file picker, so no storage permission is needed.
- Apply to the home screen, the lock screen, or both.

## Compatibility rules

- minSdk 24, targetSdk and compileSdk latest.
- Anything that needs a newer Android is checked at runtime and has a fallback.
- Icon shapes are drawn by us, so they look the same on every Android version.
- Minimal permissions. Keep a running list of OEM quirks (Samsung, Xiaomi, Huawei) in `COMPATIBILITY.md` as they come up.
- Test on emulators at API 24, 28, 31 and the latest, including a low-memory profile.

## Milestones

| # | What you can see and try |
|---|---|
| M0 | Installable launcher you can set as your home screen (this scaffold) |
| M1 | Apps, dock, app drawer, Wallpaper Showcase style |
| M2 | Wallpaper studio: layers, blending, blur, live preview |
| M3 | Apply wallpaper to lock and home screens |
| M4 | Free Canvas: drag, resize and rotate things, edit mode with undo |
| M5 | Dashboard cards and saving/sharing styles |
| M6 | Folders, gestures, icon packs, hide apps, search, settings |
| M7 | Widgets, more styles |
| M8 | Smart suggestions, animated wallpapers, polish |

## Tech (for reference)

Kotlin, Jetpack Compose, single Gradle module for now. Room and DataStore will be added when there is data to store.
