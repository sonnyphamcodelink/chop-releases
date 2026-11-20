# Chop — Releases

**Chop** is a screenshot and annotation tool for Mac, Windows and Linux: capture a window or a region, mark it up with arrows, blur and callouts, and get it into the clipboard without leaving the keyboard. No account, one-time purchase.

[Website](https://chop.asia) · [Pricing](https://chop.asia/#pricing) · [Support](mailto:support@chop.asia)

This repo holds installers only — the source lives in a private repo. Chop's built-in **Check for Updates…** reads the newest release here.

## Download

**[→ Get the latest release](../../releases/latest)** or see [chop.asia/download](https://chop.asia/download).

| Platform | File |
| --- | --- |
| macOS, Apple silicon (M1 and later) | `Chop-mac-arm64.dmg` |
| macOS, Intel | `Chop-mac-x64.dmg` |
| Windows 10/11, 64-bit | `Chop-win-x64.exe` |
| Ubuntu 22.04/24.04 x64, Debian package (recommended) | `Chop-linux-x64.deb` |
| Ubuntu 22.04/24.04 x64, AppImage | `Chop-linux-x64.AppImage` |

Not sure which Mac you have? Apple menu → About This Mac. "Apple M…" means Apple silicon; "Intel" means the other one.

## First launch

### macOS

Chop for macOS is signed with a Developer ID and notarized by Apple, so it opens like any other app.

1. Open the `.dmg` and drag **Chop** to Applications.
2. Open Chop. The first time you capture, macOS asks for Screen Recording permission. Open **System Settings → Privacy & Security → Screen Recording**, enable **Chop**, then **quit and relaunch Chop** — macOS does not apply the grant to a running app.

Chop lives in the menu bar. There is no Dock icon.

### Windows

Windows SmartScreen may warn about an unrecognized publisher. Choose **More info → Run anyway**, then follow the installer.

### Ubuntu

Requires Ubuntu 22.04/24.04 x64 with an X11 desktop session. Wayland is not supported.

1. On the login screen, select your user and choose **Ubuntu on Xorg** from the gear menu before signing in.
2. **Debian package (recommended):** open a terminal in your download folder and run `sudo apt install ./Chop-linux-x64.deb`. Open Chop from your applications menu.
3. **AppImage:** run `chmod +x Chop-linux-x64.AppImage`, then `./Chop-linux-x64.AppImage`. You may need `libfuse2` on Ubuntu 22.04 or `libfuse2t64` on 24.04; the Debian package avoids this. Keep the application sandbox enabled.

The same steps are at [chop.asia/download#ubuntu-install](https://chop.asia/download#ubuntu-install).

## Using Chop

- **⌘⇧2** (**Ctrl+Shift+2** on Windows) — start a capture. Hover a window and click to grab it, or drag to grab a region. **Esc** cancels.
- Tools: **B** box, **A** arrow, **T** text, **H** highlighter, **X** blur, **N** callout, **C** crop.
- **⌘C** copies the annotated image and **⌘S** saves it wherever you choose. **⌘Z** and **⇧⌘Z** undo and redo. **Delete** removes the selected annotation.
- While cropping, **Enter** applies and **Esc** abandons it.
- Captures auto-save to `~/Pictures/Chop` (`Pictures\Chop` on Windows). Past captures appear in the filmstrip and reopen fully editable.

## Publishing a release

For the maintainer — the running app compares its version against the release **tag**, so the tag must be `v<version>` matching `package.json` (e.g. `v0.2.0`). Attach `Chop-mac-arm64.dmg`, `Chop-mac-x64.dmg`, `Chop-win-x64.exe`, `Chop-linux-x64.deb` and `Chop-linux-x64.AppImage` under exactly those names: chop.asia links to `releases/latest/download/<file>`.
