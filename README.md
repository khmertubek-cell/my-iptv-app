# IPTV PLAYER — Android Studio starter project

A starter Android IPTV player project with:
- TV Live / Movies / Series tabs
- M3U and M3U8 URL import, plus pasted M3U text
- Xtream Codes account connection
- Media3 / ExoPlayer playback
- Android TV launcher category and D-pad-friendly focusable controls
- Configurable date expiry check and device ID display
- GitHub Actions workflow to build and upload a debug APK

## Open in Android Studio
1. Extract this ZIP.
2. Open the `IPTV_PLAYER` folder in Android Studio.
3. Allow Gradle sync and install Android SDK 35 if prompted.
4. Run on an Android device / Android TV, or use Build > Build Bundle(s) / APK(s) > Build APK(s).

## Build APK with GitHub Actions
1. Create a GitHub repository and upload the project contents (the `.github` folder must be included).
2. Open the repository's **Actions** tab.
3. Select **Android APK Build**.
4. Click **Run workflow** (or push to `main` / `master`).
5. Open the completed workflow run and download **IPTV-PLAYER-debug-apk** under Artifacts.

## Configure expiry date
Edit `app/build.gradle`:
`buildConfigField 'String', 'EXPIRY_DATE', '"2027-12-31"'`
Use `yyyy-MM-dd`, then rebuild.

## Important licensing notes
This starter checks a locally configured expiry date and shows the Android device ID. It does **not** yet provide secure remote device activation, subscription renewal, or tamper-resistant licensing. Those require a backend API and server-side license database; do not use a hard-coded client secret for production licensing.

## Xtream compatibility note
The sample imports live streams, VOD entries, and series entries from Xtream-compatible endpoints. Series playback commonly requires a separate `get_series_info` request to resolve a selected episode; this starter lists series entries but does not yet implement season/episode browsing. Playlist group filtering is based on M3U `group-title` text. Use only playlists and streams you are authorized to access.
