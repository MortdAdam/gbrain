# CachyOS / Arch: portable Expo → arm64 APK build

Exact sequence used to build a sideloadable APK on a machine with no Android SDK/JDK.
Env: CachyOS x86_64, bun/npm, Python uv. Target: arm64-v8a phone (e.g. iQOO Z9x).

## 1. JDK 17 (portable, no sudo)
```bash
JDK_PKG=$(pacman -Sp --print-format '%l' jdk17-openjdk | tail -1)
mkdir -p "$HOME/.local/share/jdks/arch17"
curl -fL --retry 3 "$JDK_PKG" -o /tmp/jdk17.pkg.tar.zst
bsdtar -xf /tmp/jdk17.pkg.tar.zst -C "$HOME/.local/share/jdks/arch17"
JAVA_HOME="$HOME/.local/share/jdks/arch17/usr/lib/jvm/java-17-openjdk"
"$JAVA_HOME/bin/java" -version
```
(Adoptium GitHub API is rate-limited / TLS-timeout-prone here; pacman direct URL is reliable.)

## 2. FIX Arch JDK java.security break (Gradle dies without this)
Arch JDK ships `conf` as a symlink to `/etc/java17-openjdk`; Gradle errors with
`Error loading java.security`. Repair:
```bash
rm "$JAVA_HOME/conf"
ln -s ../../../../etc/java17-openjdk "$JAVA_HOME/conf"
"$JAVA_HOME/bin/java" -XshowSettings:properties -version 2>&1 | grep java.home
```

## 3. Android SDK via Google android CLI installer
```bash
curl -fsSL https://dl.google.com/android/cli/latest/linux_x86_64/install.sh | bash
# installer lands at ~/.local/bin/android
export PATH="$HOME/.local/bin:$PATH"
android sdk install platforms/android-35 build-tools/35.0.0 platform-tools ndk/26.1.10909125
android sdk install cmake/3.22.1   # if Gradle asks for CMake
export ANDROID_HOME="$HOME/Android/Sdk"
export ANDROID_SDK_ROOT="$ANDROID_HOME"
```

## 4. Generate native project
```bash
cd /path/to/expo-app
npx expo prebuild --platform android --clean --no-install
```

## 5. Build release (arm64 only — keeps APK < 50MB for Telegram)
Set in `android/gradle.properties`:
```
reactNativeArchitectures=arm64-v8a
```
```bash
export JAVA_HOME="$HOME/.local/share/jdks/arch17/usr/lib/jvm/java-17-openjdk"
export ANDROID_HOME="$HOME/Android/Sdk"
export ANDROID_SDK_ROOT="$ANDROID_HOME"
export NODE_ENV=production
export PATH="$JAVA_HOME/bin:$ANDROID_HOME/platform-tools:$PATH"
cd android
./gradlew :app:assembleRelease -PreactNativeArchitectures=arm64-v8a --no-daemon --console=plain
```

## 6. Verify + locate
```bash
APK=app/build/outputs/apk/release/app-release.apk
stat -c '%n %s bytes' "$APK"
unzip -Z1 "$APK" | grep '^lib/'            # arm64-v8a must appear; trimming others saves ~20MB
"$ANDROID_HOME/build-tools/35.0.0/aapt" dump badging "$APK"      # package, versionCode, native-code, permissions
"$ANDROID_HOME/build-tools/35.0.0/apksigner" verify --verbose "$APK"
sha256sum "$APK"
```
For Telegram Bot API the file must be < 50MB; universal (4 ABIs) is ~55MB — arm64-only is ~35MB.

## Pitfalls
- `npm run android` fails with no SDK/device — use prebuild + gradlew.
- `-PreactNativeArchitectures=arm64-v8a` alone does NOT strip prebuilt AAR libs; set
  `reactNativeArchitectures=arm64-v8a` in gradle.properties for a real shrink.
- Use `--no-daemon --console=plain` in flaky-network envs (daemon + TLS timeouts hang).
- aapt/apksigner are under `$ANDROID_HOME/build-tools/<ver>/`, not on PATH.
