# UmbraStream

> Formerly **NovaStream**. Installations from 0.5.4 or earlier update to UmbraStream automatically and keep all their data.

![UmbraStream intro](assets/umbrastream-intro.png)

UmbraStream is a personal media server to organize and play your movies, TV shows, music and photos. It runs on your own computer and keeps progress, favorites and preferences for each account.

**[Download UmbraStream](https://github.com/MitsuriKan255/UmbraStream-Downloads/releases/latest)** · [What's new](https://github.com/MitsuriKan255/UmbraStream-Downloads/releases) · [Report a problem](https://github.com/MitsuriKan255/UmbraStream-Downloads/issues)

## Choose your download

Download the installer for your system. It installs two apps:

- **UmbraStream Server**: the server. It organizes your movies, shows, music and photos and shares them with your devices.
- **UmbraStream Player**: the app to watch your library without a browser, on the same computer or another one.

| System | Installer | Requirements |
| --- | --- | --- |
| [macOS](https://github.com/MitsuriKan255/UmbraStream-Downloads/releases/latest) | `UmbraStream-…-macOS.pkg` | Mac with Apple Silicon and macOS 13.5 or later. Intel Macs can use [0.3.9](https://github.com/MitsuriKan255/UmbraStream-Downloads/releases/tag/v0.3.9), their last version. |
| [Windows](https://github.com/MitsuriKan255/UmbraStream-Downloads/releases/latest) | `UmbraStream-…-Windows-Setup.exe` | Windows 11 on an x64 PC with an Intel or AMD processor. |

The ZIP files in each release are used by the automatic updates; you don't need to download them.

## Install

1. Open the installer and follow the steps.
   - **Mac:** installs UmbraStream Server and UmbraStream Player in Applications. It asks for your Mac password.
   - **Windows:** choose what to install. It installs for your user, without administrator rights, with Start menu shortcuts. If you see "Windows protected your PC", click "More info" and "Run anyway".
2. Open **UmbraStream Server**, find its icon in the macOS menu bar or next to the Windows clock, and create your administrator account.
3. Add your folders in **Administración → Bibliotecas** (Administration → Libraries). You can browse the server's folders or paste their paths.
4. Open **UmbraStream Player** to watch your library. On the server's computer, **Abrir como app** (Open as app) opens it already connected. On another computer, type the address shown in **Administración → General → Acceso desde la red local** (local network access) and sign in.

If FFmpeg and FFprobe are missing, the server downloads and verifies them on first launch.

The apps' interface is in Spanish.

### If macOS won't open the installer or the apps

UmbraStream is not notarized by Apple. If macOS won't open the installer, go to **System Settings → Privacy & Security** and click **Open Anyway**. You can also remove the quarantine flag from **Terminal**:

```sh
xattr -d com.apple.quarantine ~/Downloads/UmbraStream-*-macOS.pkg
```

If an app says it "is damaged", remove the quarantine flag the same way, using the app's path:

```sh
xattr -dr com.apple.quarantine "/Applications/UmbraStream Server.app"
```

If you don't know the path, type `xattr -dr com.apple.quarantine ` (with a trailing space), drag the file into the Terminal window and press Return.

## Features

- Detail pages with metadata, artwork and logos. Supports Jellyfin NFO files and images from your media folders.
- Direct play, audio and subtitle selection, and transcoding with VideoToolbox on macOS and Intel Quick Sync or AMD AMF on Windows.
- Per-library settings, folder watching, watch history and backups, including automatic daily backups.
- Catalog, search, next episodes and resume across devices for each account.
- Access from other devices on your home network or Tailscale; connections from the internet are always rejected.

H.264, HEVC and AV1 support and 2160p playback depend on your hardware, browser and playback mode. **Mostrar logs** (Show logs) in the server menu and **Administración → Diagnóstico de vídeo** (video diagnostics) help you check them.

## Update

UmbraStream Server and UmbraStream Player check for a new version every day and let you know. You can also click **Buscar actualizaciones** (Check for updates) in each app's menu. Choose **Actualizar y reiniciar** (Update and restart) to install it: the app downloads it, verifies its SHA-256 checksum and keeps your data.

If you're on **0.3.8 or earlier**, download and install the latest version once. Each release includes `SHA256SUMS.txt` to verify the files.

| System | Data folder |
| --- | --- |
| macOS | `~/Library/Application Support/NovaStream` |
| Windows | `%LOCALAPPDATA%\NovaStream` |

The data folders keep the NovaStream name so existing installations keep their data.

## Support and license

When you report a problem, include your version, operating system and the steps to reproduce it. You can see the running version in the server dashboard.

This repository contains UmbraStream's downloads and release notes. The project is developed in a private repository and distributed under its [personal use license](LICENSE). Third-party components keep their own licenses.
