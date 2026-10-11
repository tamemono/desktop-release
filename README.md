<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/lockup-dark-1200.png">
    <img src="assets/lockup-light-1200.png" alt="Tamemono" width="360">
  </picture>
</p>

<p align="center">
  Desktop app for <b>Tamemono</b> - local-first study notes with optional end-to-end encrypted sync.
</p>

<p align="center">
  <a href="https://github.com/tamemono/desktop-release/releases/latest"><b>⬇ Download the latest version</b></a>
</p>

> [!NOTE]
> **Internal testing.** Builds here are early. Expect rough edges, and keep an
> export of anything important (**Export all (ZIP)** in the app menu).
>
> This repository only hosts installers and the auto-update feed. The source
> code is not published here.

## Download

Open the [latest release](https://github.com/tamemono/desktop-release/releases/latest) and pick the file for your computer:

| System | File |
|---|---|
| Windows 10 / 11 (64-bit) | `Tamemono-Setup-<version>.exe` |
| macOS, Apple Silicon (M1 and later) | `Tamemono-<version>-arm64.dmg` |
| macOS, Intel | `Tamemono-<version>-x64.dmg` |

Not sure which Mac you have? Apple menu → **About This Mac**: "Chip Apple M…" means Apple Silicon, "Processor Intel…" means Intel.

The `.zip`, `.blockmap` and `latest*.yml` files are used by the updater. You don't need to download them.

## Install

The app is **not code-signed yet**, so Windows and macOS warn you the first time. This is expected for now.

### Windows

1. Run `Tamemono-Setup-<version>.exe`.
2. If you see **"Windows protected your PC"**, click **More info** → **Run anyway**.
3. Follow the installer. It installs for your user only and doesn't need admin rights.

### macOS

1. Open the `.dmg` and drag **Tamemono** into **Applications**.
2. Open Tamemono from Applications. macOS will refuse the first time ("Apple could not verify…").
3. Go to **System Settings → Privacy & Security**, scroll down and click **Open Anyway** next to the Tamemono message. Then confirm with **Open**.
   - On macOS 14 and earlier you can also right-click the app → **Open** → **Open**.
4. If macOS says the app **"is damaged and can't be opened"**, run this once in Terminal, then open it again:
   ```bash
   xattr -cr /Applications/Tamemono.app
   ```

## Updates

- **Windows:** updates download in the background and install the next time you quit Tamemono.
- **macOS:** Tamemono tells you when a new version is out and opens this page. Download the new `.dmg` and drag it into Applications to replace the old app. Your notes stay where they are. Automatic install on macOS will come once the app is signed.

## Your data

Notes are stored on your computer and encrypted on disk with a key protected by your system keychain (Windows DPAPI / macOS Keychain):

- Windows: `%APPDATA%\Tamemono`
- macOS: `~/Library/Application Support/Tamemono`

> [!WARNING]
> Don't delete `datakey.json` or `Local State` in that folder, and don't copy the
> folder to another computer or user account. Without them, the notes on this
> computer can't be read anymore. Notes that were synced can be restored by
> signing in again. Notes that were never synced can't be.

Uninstalling keeps this folder, so reinstalling brings your notes back.

Signing in (email code) is optional. It only turns on end-to-end encrypted sync between your devices. The server can't read your notes.

## Feedback

Found a bug? [Open an issue](https://github.com/tamemono/desktop-release/issues/new) with your Tamemono version (**Help → About Tamemono** in the app menu), your OS, and the steps to reproduce it. Please don't paste note contents you want to keep private.
