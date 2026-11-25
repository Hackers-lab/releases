# Vidyut Manchitra (XVMD) — Windows 11 Assistant

Lightweight Windows 11 compatibility utility for **Vidyut Manchitra (XVMD)**. Resolves XVMD startup and login hangs on Windows 11 where `wmic.exe` is no longer present by default.

## What's New in v2.8
- **Removed Full-Screen / Resizable Window Option**: Focuses strictly on Windows 11 compatibility and launching XVMD without modifying `app.asar`.
- **Improved UI**: Modern status card with live `ACTIVE` / `NOT APPLIED` badge, installed `xvmd.exe` detection, DPI awareness, and clean action buttons.
- **Application Icon**: Added the official XVMD application icon to the executable, titlebar, and taskbar.

## Features
- **One-Click Windows 11 Fix**: Installs a lightweight `wmic.exe` compatibility shim in `%LOCALAPPDATA%\Microsoft\WindowsApps\wmic.exe` so `xvmd.exe` can query disk serial numbers on Windows 11.
- **Clean Revert**: Removes the shim with a single click if you want to undo the change.
- **Live Status Detection**: Automatically checks whether the compatibility shim is active and whether `xvmd.exe` is installed in `Program Files (x86)` or `Program Files`.
- **Direct Launcher**: Launch Vidyut Manchitra (XVMD) directly from the assistant.
- **Standalone Executable**: Single ~135 KB native Windows `.exe` with no external dependencies.

## Usage
1. Download `XVMD_Windows11_Manager_v2.8.exe` from Releases.
2. Run `XVMD_Windows11_Manager_v2.8.exe`.
3. Click **Apply Windows 11 Compatibility Fix**.
4. Click **Launch Vidyut Manchitra (XVMD)** to start the app.
