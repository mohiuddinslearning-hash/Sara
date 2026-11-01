# SARA AI — Native Android foundation

This is a Kotlin + Jetpack Compose Android Studio project (not a website or WebView).
Minimum Android version: API 26. Compile/target SDK: 35.

## Open and build
1. Install Android Studio with Android SDK 35 and JDK 17.
2. Open this folder in Android Studio.
3. Allow Gradle sync.
4. Run the `app` configuration on an emulator/device.

CLI build (after installing Android SDK and Gradle wrapper):
`gradle :app:assembleDebug`

The project archive does not include a compiled APK. No build or emulator test has been run in this environment.

## Current implementation
- Native Compose dashboard and bottom navigation.
- Bengali-first dashboard and chat UI.
- Voice recognition intent hand-off to Android speech UI (device speech service and permission availability apply).
- Native shortcuts to Wi-Fi, Bluetooth, display, sound, battery, location and general Android settings.
- Provider selector and API-key entry UI (not yet connected to provider APIs).

## Not yet implemented
The full requested product is larger than this foundation. AI provider networking/streaming, secure key persistence, Room conversation history, real TTS, wake-word service, reminders/calendar, weather/news APIs, image generation, file extraction, accessibility automation, profile export/deletion, full permission center, tests and release signing remain incomplete. UI labels must not be interpreted as completed capabilities.

## Security notes
- Do not put API keys in source code or commit them.
- The current API-key field is intentionally transient and is not persisted or transmitted.
- No accessibility service, background microphone listener, hidden recording, or silent consequential action is included.
- Calls/messages/calendar changes should require explicit user confirmation in a production implementation.

## Airaa migration
No Airaa APK/source was supplied. This project is a clean-room SARA foundation; no claim is made that Airaa-specific features have been inventoried or migrated.


## Build a Debug APK automatically on GitHub

This repository includes `.github/workflows/android-debug.yml`.

1. Create a new **public or private GitHub repository**.
2. Upload all files and folders from this project ZIP to the repository root (keep the `.github/workflows` folder).
3. Commit to the `main` or `master` branch.
4. Open the repository's **Actions** tab. The workflow named **Build SARA Debug APK** runs automatically.
5. Wait for the workflow to finish. Open the successful run and download the **SARA-debug-apk** artifact.
6. Extract the downloaded artifact ZIP. It contains `app-debug.apk`, which can be installed on a compatible Android device.

You can also start a build manually from **Actions → Build SARA Debug APK → Run workflow**.

The workflow uses JDK 17, Android SDK 35, and Gradle 8.9. It compiles the current source; it does not make unfinished features functional. The current project is an early foundation, not the complete assistant described in the product specification.
