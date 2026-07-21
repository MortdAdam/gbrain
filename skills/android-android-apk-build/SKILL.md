---
name: android-android-apk-build
version: 1.0.0
description: Build a sideloadable Android APK (arm64) from an Expo/React Native app on a machine with no pre-installed Android SDK — covers portable JDK17 + Android cmdline-tools install on CachyOS/Arch, the Arch JDK conf-symlink fix, Expo prebuild, Gradle assembleRelease, ABI shrinking for Telegram's 50MB cap, and aapt/apksigner verification.
tools:
  - terminal
  - patch
  - write_file
mutating: true
triggers:
  - "android-android-apk-build"
---

# Android APK Build (Expo/RN, no pre-installed SDK)

## When to use
User wants a `.apk` they can sideload onto a physical Android phone from an Expo (managed or
bare) or React Native project, and the build machine has **no Android SDK/JDK** installed.

## Decision: portable toolchain
Install everything locally; do not assume SDK presence.
- JDK 17 (Gradle/AGP needs it)
- Android cmdline-tools + a platform (android-35) + build-tools + platform-tools + NDK
  (RN native modules need CMake/NDK)

## Steps (CachyOS / Arch)

See `references/cachyos-build.md` for the exact, copy-paste sequence. Highlights:

1. **JDK 17** — `pacman -Sp --print-format '%l' jdk17-openjdk` to get the direct pkg URL,
   `curl` it, `bsdtar -xf` into `~/.local/share/jdks/arch17`. (Avoid Adoptium GitHub API:
   rate-limited / TLS timeouts in this environment.)
2. **FIX Arch JDK `java.security` break** — Arch's JDK ships `conf` as a symlink to
   `/etc/java17-openjdk`; Gradle dies with `Error loading java.security`. Repair:
   `rm "$JAVA_HOME/conf"; ln -s ../../../../etc/java17-openjdk "$JAVA_HOME/conf"`.
3. **Android SDK** — Google's `android` CLI installer:
   `curl -fsSL https://dl.google.com/android/cli/latest/linux_x86_64/install.sh | bash`
   (lands in `~/.local/bin/android`). Then
   `android sdk install platforms/android-35 build-tools/35.0.0 platform-tools ndk/26.1.10909125`.
   Also `android sdk install cmake/3.22.1` if Gradle asks.
4. **Native project** — `npx expo prebuild --platform android --clean --no-install`
   (or `eas build`/EAS if configured). This generates `android/` with the Gradle wrapper.
5. **Build** — set env (`JAVA_HOME`, `ANDROID_HOME`, `ANDROID_SDK_ROOT`, `NODE_ENV=production`)
   and run `./gradlew :app:assembleRelease -PreactNativeArchitectures=arm64-v8a --no-daemon --console=plain`.
   Gradle downloads its own distribution on first run.

## Telegram 50MB cap → arm64-only
A universal APK (all 4 ABIs) is ~55MB and **exceeds** Telegram Bot API's 50MB upload limit.
The `-PreactNativeArchitectures=arm64-v8a` flag alone does NOT strip prebuilt AAR libs.
Set it persistently in `android/gradle.properties`:
`reactNativeArchitectures=arm64-v8a`
then rebuild. Verify the shrunk size with `stat -c '%s bytes' app-release.apk` and the ABI
list with `unzip -Z1 app-release.apk | grep '^lib/'`.

## Verify the APK (do not claim success without this)
```
APK=android/app/build/outputs/apk/release/app-release.apk
"$ANDROID_HOME/build-tools/35.0.0/aapt" dump badging "$APK"   # package, versionCode, native-code, permissions
"$ANDROID_HOME/build-tools/35.0.0/apksigner" verify --verbose "$APK"
unzip -Z1 "$APK" | grep '^lib/'
sha256sum "$APK"
```
Target device (e.g. iQOO Z9x, Snapdragon 6 Gen 1, aarch64) needs `arm64-v8a` present.
Confirm `native-code` includes `arm64-v8a` and signature verifies (APK Signature Scheme v2+).

## Pitfalls
- `npm run android` fails without an SDK/device — use `prebuild` + `gradlew assembleRelease`.
- AccessibilityService in a native module must be `android:exported="true"` and guarded by
  `android.permission.BIND_ACCESSIBILITY_SERVICE`; filter bank/allowed packages explicitly.
- Use `--no-daemon --console=plain` for long builds in constrained/flaky-network envs
  (Gradle daemon + TLS timeouts otherwise hang).
- `aapt`/`apksigner` live under `$ANDROID_HOME/build-tools/<ver>/`, not on PATH by default.

## References
- `references/cachyos-build.md` — full command sequence (JDK, SDK, fix, build, verify).

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
