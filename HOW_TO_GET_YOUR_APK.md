# How to get your AetherNotes .apk

This project is now fully wired up as a native Android app (via Capacitor) with
its own launcher icon and splash screen. What's left is a **compile step** that
has to happen somewhere with access to Google's Android build servers — which
this chat environment does not have. Below are two ways to finish it, both free.

## Option A — GitHub Actions (no install, ~3 minutes, recommended)

1. Create a new repo on GitHub and push this entire folder to it.
2. Go to the repo's **Actions** tab. The included workflow
   (`.github/workflows/build-android.yml`) runs automatically on push.
3. When it finishes (green check), open the workflow run and download the
   **AetherNotes-debug-apk** artifact — that's your installable `.apk`.
4. Transfer it to your phone (email, Drive, USB, etc.), open it, and allow
   "install unknown apps" for that source when prompted.

You can also trigger it manually anytime from Actions → "Build Android APK" →
**Run workflow**.

## Option B — Build locally with Android Studio

1. Install [Android Studio](https://developer.android.com/studio) (it installs
   the Android SDK and Gradle for you).
2. Open the `android/` folder in this project as an existing project.
3. Let it sync, then **Build → Build Bundle(s)/APK(s) → Build APK(s)**.
4. Find the APK in `android/app/build/outputs/apk/debug/app-debug.apk`, or
   click **Run ▶** to install straight to a connected phone/emulator.

If you later change the web source (`src/`), re-run `npm run build && npx cap
sync android` before rebuilding in Android Studio.

## What was fixed/added to make this build-ready

- Restored `src/vite-env.d.ts` (missing from the upload — standard Vite file,
  needed for the CSS import to type-check).
- Fixed lost executable permissions on `node_modules/.bin/*` (zip files don't
  always preserve the executable bit).
- Installed the missing `@rollup/rollup-linux-x64-gnu` optional dependency.
- Installed `@capacitor/core`, `@capacitor/cli`, `@capacitor/android` and ran
  `npx cap add android` to generate the native project in `android/`.
- Generated a proper launcher icon + splash screen from `public/favicon.svg`
  (previously the app would have shipped with Capacitor's placeholder icon).
- Added `.github/workflows/build-android.yml` for one-click cloud builds.

The production web build itself completed successfully with no errors beyond
the above environment issues — no application logic was changed.
