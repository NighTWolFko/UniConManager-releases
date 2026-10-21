# UniConManager — releases

UniConManager is a desktop connection manager: SSH terminals, RDP, SFTP, VPN (Fortinet SSL and OpenConnect) and Kubernetes clusters in one window, with folders whose settings connections inherit, an encrypted credential vault and session logs. It runs on macOS (Apple Silicon), Fedora (x86_64) and Windows 10/11 (x64).

This repository only holds the releases. Download the newest one from **[Releases](../../releases/latest)**.

## Which file

| System | File |
|---|---|
| macOS (Apple Silicon) | `UniConManager-<version>-arm64.dmg` |
| Fedora (x86_64) | `uniconmanager-<version>.x86_64.rpm` |
| Windows 10/11 (x64) | `UniConManager-Setup-<version>-x64.exe` |

The other files (`…-mac.zip`, `latest*.yml`, `.blockmap`) are used by the app's own updates; you don't need them.

## First start

**macOS.** Open the DMG and drag **UniConManager** to **Applications**. The app is not notarized by Apple, so the first start says "Apple could not verify “UniConManager” is free of malware". Click **Done**, then either:

- open **System Settings → Privacy & Security**, click **Open Anyway** next to "UniConManager was blocked" and confirm, or
- run once in Terminal: `xattr -dr com.apple.quarantine /Applications/UniConManager.app`

**Fedora.**

```bash
sudo dnf install ./uniconmanager-<version>.x86_64.rpm
```

**Windows.** Run the installer (per user, no administrator rights). It is not signed yet: on **"Windows protected your PC"** choose **More info → Run anyway** once.

## Checking a download

Each release has `SHA256SUMS.txt`:

```bash
shasum -a 256 -c SHA256SUMS.txt --ignore-missing   # macOS
sha256sum -c SHA256SUMS.txt --ignore-missing       # Fedora
```

## Updates

From version 0.4.0 on, UniConManager checks this page by itself (at start and every 6 hours; **Check for Updates…** in the app menu, or **Help** on Windows and Linux). When a new version is out, a banner offers **Update now**, **Update when closed** or **Update later**. Nothing is installed without your choice, and the app sends nothing about you: a check is a plain download of a small file from here.

- On macOS the first start after an update may ask once whether UniConManager may use its Keychain item (the remembered vault password): allow it.
- On Fedora installing an update asks for an administrator password.
