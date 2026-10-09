# Ubuntu-Launcher
Ubuntu style android launcher with dumb phone mode
# Ubuntu Launcher for Android
### Version 1.0.3.001

**An Ubuntu-inspired desktop and smartphone launcher for Android.**

Developed by **Maclean Of Duart Enterprises Corp**

Ubuntu Launcher is a customizable, open-source Android HOME launcher designed to bring the appearance, functionality, and navigation style of Ubuntu Linux to Android smartphones.

The application combines a traditional smartphone interface with a desktop-inspired environment, automatically adapting its layout when switching between portrait and landscape orientations.

Ubuntu Launcher also includes Dumb Phone Mode, allowing users to simplify their devices without sacrificing customization or the familiar Ubuntu appearance.

---

## Features

### Ubuntu-Inspired Desktop

- Ubuntu-inspired aubergine and orange interface.
- Automatic portrait and landscape orientation support.
- Desktop-style interface optimized for landscape orientation.
- Customizable taskbar and desktop shortcuts.
- Main desktop and optional secondary desktop page.
- Configurable desktop grid with 2–8 columns.
- Custom desktop text and appearance settings.
- Support for touch navigation and configurable swipe gestures.

### Independent Portrait and Landscape Settings

Each orientation has its own display configuration.

**Settings → Display Settings → Portrait Orientation**

**Settings → Display Settings → Landscape Orientation**

Both include:

- Regular launcher wallpaper management.
- Independent Dumb Phone Mode wallpaper management.
- Single-image wallpaper selection.
- Multiple-image wallpaper slideshows.
- Wallpaper removal and restoration of the default background.
- Wallpaper scaling options:
  - Crop
  - Fill
  - Fit
  - Zoom
- Customizable clock and date.
- Clock visibility, size, color, and font.
- Desktop column configuration.
- Custom text.
- Border design preferences.

Portrait and landscape settings can be configured independently.

### Customizable Taskbar

The taskbar provides quick access to pinned applications.

Features include:

- Pin and unpin applications.
- Scrollable taskbar supporting numerous pinned applications.
- Adjustable taskbar size.
- Configurable positioning:
  - Bottom
  - Top
  - Left
  - Right
- Always-visible mode.
- Hidden mode.
- Automatic hiding.
- Customizable auto-hide duration in seconds.
- Taskbar reveal button when hidden.
- Application drawer shortcut.

Applications are pinned to the taskbar rather than automatically populating the desktop.

### Application Drawer

The application drawer provides access to installed applications.

Features include:

- Application search.
- Grid view.
- List view.
- Application launching.
- Application pinning and unpinning.
- Launcher settings access.
- Hidden application filtering.
- Dumb Phone Mode application filtering.

### Desktop Files and Website Shortcuts

Ubuntu Launcher supports desktop shortcuts similar to a traditional computer desktop.

Users can:

- Pin local files.
- Add website shortcuts.
- Receive shared website links.
- Receive shared files.
- Rename shortcuts.
- Remove shortcuts.
- Display image previews for supported files.
- Display website favicons.
- Open files using compatible Android applications.
- Open website links using the device's browser.

Shortcuts can be placed on the main desktop or an optional secondary desktop page.

### Dumb Phone Mode

Dumb Phone Mode provides a simplified Android environment while maintaining the Ubuntu visual appearance.

Features include:

- Enable or disable Dumb Phone Mode.
- Select which applications are accessible through the launcher.
- Maintain an independent application allowlist.
- Customize Dumb Phone Mode backgrounds.
- Configure notification filtering.
- Access Dumb Phone Mode settings from the launcher settings menu.

Dumb Phone Mode is designed to reduce distractions without requiring a separate launcher.

### Hidden Applications

Ubuntu Launcher includes application hiding functionality.

Hidden applications are excluded from:

- The normal application drawer.
- Launcher search.
- Desktop application selections.
- Dumb Phone Mode application lists.

Hidden applications remain manageable through Launcher Settings.

**Note:** Application hiding operates within Ubuntu Launcher and does not disable or uninstall applications at the Android system level.

### Clock and Date Customization

The launcher includes a configurable desktop clock.

Available options include:

- Clock visibility.
- Adjustable text size.
- Custom text color.
- Multiple font styles.
- Date and time display.
- Independent portrait and landscape configurations.

The clock updates automatically to reflect the device's current time.

### Weather Application Integration

Users can select a weather application and configure whether its shortcut appears on the desktop.

The weather shortcut can be enabled or disabled without removing the selected application.

**Note:** The current weather integration uses an application shortcut rather than a fully interactive Android weather widget.

### Launcher Lock

Ubuntu Launcher includes an optional Ubuntu-inspired launcher lock interface.

Features include:

- Enable or disable the launcher lock.
- Configure a PIN or password.
- Ubuntu-inspired lock-screen appearance.
- Clock and date display.

**Important:** This feature does not replace Android's secure system lock screen.

### Launcher Backup and Restore

Launcher settings can be exported and restored.

Features include:

- Export launcher configuration to a JSON backup.
- Save backups using Android's document picker.
- Import previously exported configurations.
- Restore launcher preferences.

This allows users to preserve their launcher configuration when reinstalling or transferring settings.

---

## Technical Information

| Property | Details |
|----------|---------|
| Application | Ubuntu Launcher |
| Version | 1.0.3.001 |
| Version Code | 5 |
| Developer | Maclean Of Duart Enterprises Corp |
| Package ID | com.macleanofduartenterprises.ubuntulauncher |
| Platform | Android |
| Minimum Android API | 26 |
| Target Android API | 35 |
| Programming Language | Kotlin |
| Interface Framework | Jetpack Compose |
| Build System | Gradle 8.9 |
| Java Version | JDK 17 |
| License | GNU AGPLv3 |

The project uses Android's native launcher functionality and is designed to operate as the device's default HOME application.

---

## Installation

### Install the APK

1. Download the latest Ubuntu Launcher APK.
2. Open the APK on your Android device.
3. Allow installation from the selected source if Android requests permission.
4. Install Ubuntu Launcher.
5. Open the application.
6. Select Ubuntu Launcher as your default HOME application.

Depending on your Android device, the default launcher can also be changed through:

**Android Settings → Apps → Default Apps → Home App**

### Updating

When installing a newer version, the APK must use the same package ID and a compatible signing certificate as the currently installed version.

Using a consistent signing key allows compatible updates without uninstalling the application.

---

## Building From Source

Ubuntu Launcher can be built using Android Studio or GitHub Actions.

### Requirements

- JDK 17
- Android SDK
- Gradle 8.9
- Android SDK Platform 35
- Kotlin and Jetpack Compose dependencies

### Debug Build

Run:

```bash
./gradlew --no-daemon assembleDebug
```

The resulting APK will be located at:

```text
app/build/outputs/apk/debug/app-debug.apk
```

### Release Build

Run:

```bash
./gradlew --no-daemon lintRelease assembleRelease
```

Release builds support code optimization and resource shrinking.

### APK Signing

Release signing credentials are supplied through environment variables.

```text
ANDROID_KEYSTORE_PATH
ANDROID_KEYSTORE_PASSWORD
ANDROID_KEY_ALIAS
ANDROID_KEY_PASSWORD
```

Signing credentials and private keystore files must never be committed to the public source repository.

GitHub Actions can use encrypted repository secrets to produce consistently signed APK releases.

---

## Open-Source License

Ubuntu Launcher is licensed under the:

**GNU Affero General Public License, Version 3 (AGPLv3)**

The complete license is included in the repository and within the application.

Access it through:

**Launcher Settings → Licenses**

The AGPLv3 permits users to use, study, modify, and redistribute the software under its license terms.

Modified versions distributed under the license must comply with the applicable source-code and copyleft requirements.

Commercial use is permitted under the AGPLv3.

---

## Android Platform Limitations

Ubuntu Launcher operates as an Android HOME launcher.

Certain Android system functions remain controlled by the operating system, including:

- System-level device locking and authentication.
- Android's secure keyguard.
- Certain notification-management capabilities.
- System navigation and Recent Apps functionality.
- System-level application restrictions.

Ubuntu Launcher does not replace Android itself.

It provides a customizable launcher environment running on Android.

---

## Developer

**Maclean Of Duart Enterprises Corp**

Independent software development, open-source technology solutions, and IT services.

**Website:** macleanofduartenterprises.com

**Email:** office@macleanofduartenterprises.com

**Phone:** +1 (717) 500-6202

---

## Trademark Notice

Ubuntu and the Ubuntu logo are registered trademarks of Canonical Ltd.

Ubuntu Launcher is an independent software project developed by Maclean Of Duart Enterprises Corp.

The project is not officially affiliated with, sponsored by, or endorsed by Canonical Ltd.

---

## Project Philosophy

Ubuntu Launcher is developed to provide a customizable, practical, and open-source alternative to conventional Android launchers.

Its primary objectives are:

- User control and customization.
- Open-source development.
- A desktop-inspired Android experience.
- Simplified device operation when desired.
- Independence from proprietary launcher ecosystems.
- Practical functionality for everyday smartphone use.

**Ubuntu Launcher — Bringing the desktop experience to Android.**

Copyright © 2026 Maclean Of Duart Enterprises Corp.

Licensed under GNU AGPLv3.
**Developer:** Maclean Of Duart Enterprises Corp

## License

Ubuntu Launcher is free and open-source software licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

The complete AGPLv3 license is included with the source and can also be viewed inside the application under:

**Ubuntu Launcher Settings → Licenses**

## Trademark Notice

Ubuntu and the Ubuntu logo are registered trademarks of Canonical Ltd.

Ubuntu Launcher is an independent open-source project and is not endorsed by or affiliated with Canonical Ltd.
