# Chop — Releases

Downloads for **Chop**, a screen capture and annotation tool for macOS and
Windows. Capture a region or a window with one click, mark it up, and get it
into the clipboard or a folder.

This repo holds installers only — the source lives in a private repo. Chop's
built-in **Check for Updates…** reads the newest release here.

## Download

**[→ Get the latest release](../../releases/latest)**

| Platform | File |
| --- | --- |
| macOS, Apple Silicon (M1–M4) | `Chop-<version>-arm64.dmg` |
| macOS, Intel | `Chop-<version>.dmg` |
| Windows 10/11, 64-bit | `Chop Setup <version>.exe` |

Not sure which Mac you have? Apple menu → About This Mac. "Apple M…" means
Apple Silicon; "Intel" means the other one.

## First launch

### macOS

Chop is ad-hoc signed rather than notarized, so Gatekeeper will not open it on a
double-click.

1. Open the `.dmg` and drag **Chop** to Applications.
2. In Applications, **right-click Chop → Open**, then confirm. You only need to
   do this once.
3. Choecording permission to capture anything. Open
   **System Settings → Privacy & Security → Screen Recording**, enable **Chop**,
   then **quit and relaunch Chop** — macOS does not apply the grant to a running
   app.

Chop lives in the menu bar. There is no Dock icon.

### Windows

Windows SmartScreen will warn about an unrecognized publisher. Choose
**More info → Run anyway**, then follow the installer.

## Using Chop

- **⌘⇧2** (**Ctrl+Shift+2** on Windows) — start a capture. Hover a window and
  click to grab it, or drag to grab a region. **Esc** cancels.
- Tools: **B** box, **A** arrow, **T** text, **H** highlighter, **X** blur,
  **N** callout, **C** crop.
- **⌘C** copies the annotated image, **⌘S** saves it somewhere of your choosing** undo and redo. **Delete** removes the selected annotation.
- While cropping, **Enter** applies and **Esc** abandons it.
- Captures auto-save to `~/Pictures/Chop`. Past captures appear in the filmstrip
  and reopen fully editable.

## Updating

Chop checks for a newer release when it starts and from the menu bar icon's
**Check for Updates…**. It will not install the update itself — in-place updates
need a Developer ID signature, and Chop is ad-hoc signed. When an update exists,
Chop points you at the release page.

To update: quit Chop, open the new `.dmg` or installer, and replace the old copy.

**On macOS, capture may stop working after an update.** An ad-hoc signature
changes with every build, so macOS can treat the new version as a different app
and drop its Screen Recording grant. If that happens, open **System Settings →
Privacy & Security → Scording**, remove Chop with the **–** button, add
it back with **+**, and relaunch.

## Publishing a release

For the maintainer — the running app compares its version against the release
**tag**, so the tag must be `v<version>` matching `package.json` (e.g. `v0.2.0`).
Attach the `.dmg` and `.exe` files; nothing else is required, since Chop reads
only the tag and the release page URL.
