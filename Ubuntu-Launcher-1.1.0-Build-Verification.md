# Ubuntu Launcher 1.1.0 build verification

Verified on 2026-11-02 with Eclipse Temurin JDK 17.0.21, Gradle 8.9, Android Gradle Plugin 8.7.3, Kotlin 2.0.21, compile/target SDK 35, and Android build tools 35.0.0.

## Completed checks

- `testReleaseUnitTest`: passed (39 tests across 9 suites; 0 failures, 0 errors, 0 skipped)
- `compileReleaseKotlin`: passed
- `lintVitalRelease`: passed
- `assembleRelease`: passed
- R8 code optimization: passed
- Resource shrinking and optimization: passed
- APK ZIP integrity: passed
- APK ZIP alignment: passed
- APK Signature Schemes v2 and v3: passed
- Package: `com.macleanofduartenterprises.ubuntulauncher`
- Version: `1.1.0` (`versionCode 29`)
- Minimum/target SDK: 26 / 35
- Native ABIs: ARM64, ARMv7, x86, and x86_64
- Release certificate SHA-256: `62ebb3c5d7d722b2e1174a4622f7593926204579084f94e11151ef606b32d136`
- APK SHA-256: `b646a51924879260674241a75e1a58c69d25a05a93c5bf1b1c6cc99a0c4d57da`
- APK size: 1,534,305 bytes

The package name and release certificate match the established Ubuntu Launcher release identity. Version code 29 is higher than the supplied source's version code 28, allowing Android to install 1.1.0 as a signed upgrade over earlier releases using the same key.

## Release update

- Promoted the completed application to version 1.1.0 with Android version code 29.
- Replaced destructive icon recoloring with a user-selected colored background tile and intact original application artwork.
- Draws application artwork at 78% scale over the colored tile, keeping both visual layers readable.
- Applies opacity to the combined tile-and-icon result.
- Keeps portrait and landscape preferences independent.
- Uses the same bi-color rendering in application grid and list layouts while leaving icons unchanged when recoloring is disabled.

No emulator was used. No physical Android device was attached to this build environment, so installation, gesture, overlay-permission, notification-listener, PIN-lock, keyboard, and touch-interaction behavior remain physical-device acceptance checks.

The release keystore and credentials are not included in the source archive.
