# Chat On Steroids — Android independent prototype

This is a native Android Studio starter project inspired by the public workflow of Chat On Steroids. It is **not** a full port of the original Electron application.

## Included in this prototype
- Native Android interface
- User-selected workspace folder using Android Storage Access Framework
- Local task/goal list
- Local session notes
- Local-only storage for tasks and notes
- Capability status and explicit limitations

## Not ported (requires a separate design and implementation)
- Chrome extension / ChatGPT browser automation
- MCP server and tunnel setup
- Electron desktop APIs and secure-storage integration
- Shell command execution and persistent terminal sessions
- Desktop screen, mouse, keyboard and clipboard control
- Multi-worker AI execution, Goal/Loop orchestration, Compact & Resume
- ChatGPT account integration or AI model calls

Android's application sandbox and background execution rules differ from desktop OSes. Desktop automation and unrestricted shell access should not be assumed to work on Android. This prototype does not request network or broad storage permissions.

## Build an APK
1. Install Android Studio (recent stable version) and its Android SDK Platform 35.
2. Open this folder as an existing project.
3. Allow Gradle to sync. Use JDK 17.
4. Select **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
5. Android Studio places the debug APK under `app/build/outputs/apk/debug/`.

Or, with Gradle installed and Android SDK configured, run:

```bash
gradle assembleDebug
```

## Important
- This is an early prototype and has not been built or tested on a physical device in this environment.
- The app currently saves tasks and notes on the device only.
- Choosing a workspace folder records a scoped Android document URI. Reading/writing arbitrary files is not implemented yet.
- No API keys, network calls, or AI features are included.

## Upstream project
https://github.com/totec448-spec/chat-on-steroids

The upstream project is MIT-licensed. This prototype is a separate implementation and is not affiliated with or endorsed by OpenAI.


## Build APK without Android Studio (GitHub Actions)

This project includes `.github/workflows/android.yml`. To build in GitHub's cloud:
1. Create a GitHub repository and upload the contents of this folder (including the hidden `.github` folder).
2. Open the repository's **Actions** tab.
3. Select **Build Android APK** and press **Run workflow** (or push to `main`/`master`).
4. Open the completed workflow run. Under **Artifacts**, download `ChatOnSteroids-debug-apk`.
5. Extract the artifact ZIP and install `app-debug.apk` on your Android device.

This produces a debug APK for testing, not a Play Store release. This prototype still does not include the upstream AI, MCP, browser, terminal, or desktop-control features.
