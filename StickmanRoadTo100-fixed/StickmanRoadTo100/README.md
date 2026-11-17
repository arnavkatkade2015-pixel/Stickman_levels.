# Stickman: Road to 100 – Android app

Full-screen landscape WebView wrapper for the HTML5 game.

## Quick build on GitHub (recommended, no local Android Studio needed)

1. Create a **new empty GitHub repository**.
2. Upload **all contents of this folder** to the root of the repo (including the hidden `.github` folder).
3. Go to the **Actions** tab → select **"Build Android APK"** → click **Run workflow**.
4. Wait 2–4 minutes.
5. Download the **Stickman-APK** artifact → unzip → install `app-debug.apk` on your phone.

> Important: Make sure the `.github/workflows/build.yml` file is present. GitHub hides dot-folders; when uploading via web UI you may need to drag the whole folder or use `git`.

## Local build (Android Studio)

1. Open this folder in Android Studio.
2. Let Gradle sync (JDK 17 recommended).
3. Build → Build Bundle(s) / APK(s) → Build APK(s).

## Optional offline libraries

For fully offline play (no CDN needed):

```bash
./fetch_libs.sh   # or fetch_libs.bat on Windows
```

This downloads `three.min.js` and `rapier.es.js` into `app/src/main/assets/libs/`.

## Play Store

- Change `applicationId` in `app/build.gradle` to a unique ID.
- Create a keystore and set the four env vars listed in `app/build.gradle`.
- Run `./gradlew bundleRelease`.
- Upload the `.aab` + the included `play_store_icon_512.png`.

## Controls (mobile)

- Virtual joystick + on-screen buttons (Attack, Kick, Jump, Defend, Dodge, Heal, Ultimate).
- Hold **Kick** button to open the kick selector.
- Layout button lets you rearrange / resize controls.
