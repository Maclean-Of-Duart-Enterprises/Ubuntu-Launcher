# Ubuntu Launcher 1.1.4 — build verification

Built and verified on 2026-11-10 from the attached Desktop Navigation Settings source. The standard local Android release pipeline ran entirely from the existing tool/dependency cache, without an emulator.

## Release identity

- Package: `com.macleanofduartenterprises.ubuntulauncher`
- Version name / code: `1.1.4` / `33`
- Minimum / target Android SDK: `26` / `35`
- Native ABIs: `arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64`
- Signing certificate SHA-256: `62ebb3c5d7d722b2e1174a4622f7593926204579084f94e11151ef606b32d136`
- APK SHA-256: `a1fca3d24d9b41662b77483d522755c8fc48d9aeaec6d51d82298be8ae50c85e`
- APK size: 1,550,693 bytes

The package and certificate match the established Ubuntu Launcher identity. Code 33 is higher than 1.1.3's code 32, so the APK can update correctly signed earlier releases without uninstalling or clearing launcher data.

## Completed verification

- Release Kotlin and Java compilation at JVM target 17: passed.
- `testReleaseUnitTest`: 39 tests across 9 suites; zero failures, errors, or skips.
- `lintRelease`: passed; zero reported issues.
- `assembleRelease`: passed.
- R8 minification and optimization: passed.
- Resource shrinking and optimization: passed.
- ZIP integrity and absence of duplicate APK entries: passed.
- APK ZIP alignment, including 16-KB native-library ZIP alignment: passed.
- APK Signature Schemes v2 and v3: passed; one signer matching the established certificate.
- Release is not debuggable.
- Packaged DEX includes the new Screen navigation, Screen order, Tap edge, and per-screen Add Widget controls.
- Source archive version metadata matches the APK and excludes signing keys, credentials, local SDK paths, and build caches.

Toolchain: Eclipse Temurin JDK 17.0.21, Gradle 8.9, Android Gradle Plugin 8.7.3, Kotlin 2.0.21, Android SDK 35, and build-tools 35.0.0.

## Build repairs

The attached source had malformed Add/Remove Widget click-handler expressions, including a missing lambda boundary that prevented Kotlin compilation. The handlers now invoke add/remove actions directly through the current host activity obtained from LocalActivity. The source's JVM 17 targets and supplied navigation functionality remain intact. Version metadata was raised from 1.1.3/code 32 to 1.1.4/code 33.

## Physical-device acceptance still required

No physical Android device was attached. The 39 existing unit tests cover established launcher logic, not actual touch gestures or Android widget binding/configuration. On the phone, verify in-place update and existing preferences; left/right edge taps and swipes for page navigation; independently disabled Applications/Settings actions and gesture-priority conflicts; absence of the old bottom desktop buttons; per-screen Add/Remove Widget actions from Desktop settings; screen ordering and shortcut destination; portrait/landscape behavior; and Home routing after reboot/unlock. Android-managed widget IDs are installation-specific and cannot be assumed portable through preference backup/restore.
