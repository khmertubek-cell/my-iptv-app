# PLC Cambodia TV — Android WebView app

This Android project packages the hosted website https://my-iptv-app.pages.dev/ as an installable Android app. It includes phone and Android TV launcher entry points.

## Build the APK with GitHub Actions

1. Create a new GitHub repository, for example `PLC-Cambodia-TV-Android`.
2. Upload the contents of this folder to the repository root (do not upload the outer ZIP folder itself).
3. Open **Actions** → **Build PLC Cambodia TV APK**.
4. Select **Run workflow** and run it on the main branch.
5. When the run finishes, open it and download the artifact named **PLC-Cambodia-TV-debug-apk**.
6. Extract the artifact. Install `app-debug.apk` on your Android device or Android TV.

## Notes

- This is a WebView wrapper: the website is loaded from the internet, so the device needs an internet connection.
- Website changes appear in the app automatically; no APK rebuild is needed for website-only changes.
- This is a debug APK for testing and direct installation, not a Play Store release-signed APK.
- Xtream/M3U playback and browser CORS behavior depend on the website and playlist provider. This wrapper does not bypass provider restrictions.
- The Android app does not include or provide TV channel streams.
