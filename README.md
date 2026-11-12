# SAIL auto attendance

Android app that opens an attendance app at your In and Out times, waits, taps the In or Out
button, then closes the attendance app. It runs in the background after you save the schedule.

## Build the APK

**Option A: Android Studio**
1. Open this folder in Android Studio and wait for Gradle sync.
2. Connect your phone (USB debugging on) and press Run, or use Build > Build APK(s).
3. The APK is at `app/build/outputs/apk/debug/app-debug.apk`.

**Option B: GitHub (no Android Studio)**
1. Create a GitHub repository and upload everything in this folder (the contents, not the folder).
2. Open the Actions tab, choose "Build APK", and press Run workflow.
3. When it finishes, download `SAIL-auto-attendance-apk` from the run page and install the APK.

## First-time setup on the phone
1. Open the app and press **Open** on the amber notice, then turn on **SAIL auto attendance**
   in Accessibility settings.
2. Choose the attendance app, tick the days, and set the In and Out times.
3. For each button, type its on-screen text and/or press **Pick on screen** and drag the red ring
   onto it. Use the button text when it is unique; the saved position is the backup.
4. Press **Test In now** and **Test Out now** to check, then **Save & schedule**.

## Keep it reliable
- Set the app's battery usage to **Unrestricted** and allow **Autostart** (Xiaomi, Oppo, Vivo, Realme, Samsung).
- The phone must be on. A PIN, pattern or fingerprint lock stops the tap; the app cannot unlock it.
- After updating the app, check that Accessibility is still on.
- Saved positions depend on screen size, display zoom and font size. Pick again if you change them.

## Files
- `app/src/main/java/com/example/autotapper/`
  - `MainActivity.kt` screen and settings
  - `ClickService.kt` accessibility service: taps, closes the app, on-screen position picker
  - `Scheduler.kt` alarms for In and Out, wake screen, open app; boot receiver
- `preview/sail-auto-attendance-preview.html` clickable preview of the screen
