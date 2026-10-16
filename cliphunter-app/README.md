# ClipHunter (Android)
Finds highlight clips (loudness shifts, slow-motion, intense scenes) in long videos. 100% on-device.

## Get an APK to test (no Android Studio needed)
1. Create a GitHub repo, upload this folder, set your own `appId` in `capacitor.config.json` (e.g. com.yourname.cliphunter).
2. Actions tab -> "Build Android" -> Run workflow -> download `cliphunter-builds` -> install the debug .apk.

## Publish on Google Play
1. Make a keystore: `keytool -genkey -v -keystore release.jks -alias clip -keyalg RSA -keysize 2048 -validity 10000`
2. Repo Settings -> Secrets: KEYSTORE_B64 (`base64 -w0 release.jks`), KEYSTORE_PASSWORD, KEY_PASSWORD, KEY_ALIAS.
3. Re-run the workflow; upload the signed `.aab` in Play Console (enroll in Play App Signing).
4. Needed: developer account ($25), 512px icon (`npx @capacitor/assets generate`), feature graphic, screenshots, privacy policy URL (say: no data collected, video is processed locally), content rating, Data safety form.
5. New personal accounts must run a closed test with 12+ testers for 14 days before production.

Or open locally: `npm install && npx cap sync android && npx cap open android`.
