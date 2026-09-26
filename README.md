# Termyte

Termyte is a voxel game you play in a window or in a terminal. This repository holds the
release builds and this README. The source code is private and is not published here.

Download the latest version from the
[Releases page](https://github.com/bolognesandwiches/termyte-releases/releases/latest).
The game connects to `play.termyte.net` by itself. You do not need to configure anything.

## Install

### Windows

Option 1: the installer (recommended if you do not use a terminal).

1. Download `engine-app-x86_64-pc-windows-msvc.msi` from the latest release.
2. Double-click it and follow the steps. Windows asks for administrator rights.
3. Open **Termyte** from the Start menu.

Option 2: PowerShell (installs for your user only, no administrator rights, updates itself).

```powershell
powershell -ExecutionPolicy Bypass -c "irm https://github.com/bolognesandwiches/termyte-releases/releases/latest/download/engine-app-installer.ps1 | iex"
```

Then open a new terminal and run `termyte-window` (a window) or `termyte client --terminal`
(in the terminal). The files go to `%USERPROFILE%\.termyte\bin`.

### macOS (Apple Silicon and Intel) and Linux (x86_64)

```sh
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/bolognesandwiches/termyte-releases/releases/latest/download/engine-app-installer.sh | sh
```

Then open a new terminal and run `termyte client` (a window) or `termyte client --terminal`.
The files go to `~/.termyte/bin`.

You can also download the archive for your system (`.tar.xz` or `.zip`) and unpack it anywhere.

## Warnings about unsigned builds

Termyte builds are not signed yet, so your system warns you the first time.

- **Windows SmartScreen** ("Windows protected your PC"): click **More info**, then
  **Run anyway**.
- **macOS Gatekeeper** ("cannot be opened because the developer cannot be verified"): in
  Finder, right-click (or Control-click) the file, choose **Open**, then **Open** again. On
  macOS 15 and later, try to open it once, then go to **System Settings**, **Privacy &
  Security**, and click **Open Anyway**. The terminal installer above does not trigger this
  warning.

## Updates

When a new version is out, the login screen shows **Update available**. Press the key it shows
to update and restart. When the server needs a newer version, it shows **Update required**
and you must update before you can play. The update downloads from this page and checks the
SHA-256 checksum before it installs.

Automatic updates work for the PowerShell and terminal installers. If you used the Windows
installer (`.msi`), download the new `.msi` and run it; it replaces the old version.

## Checking a download

Every file has a `.sha256` file next to it, and `sha256.sum` lists all of them. To check a file:

- Windows: `Get-FileHash <file> -Algorithm SHA256`
- macOS: `shasum -a 256 <file>`
- Linux: `sha256sum <file>`

## Licences

The window mode uses the DejaVu Sans Mono font. Its licence is in
`DejaVuSansMono-LICENSE.txt` in every archive.
