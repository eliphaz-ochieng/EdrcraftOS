# Get your APK (about 5 minutes, free)

1. Create a free account at github.com and make a **new private repository** (name it pipeline-os).
2. On the repo page click **Add file > Upload files**. Unzip this project first, then drag in **everything inside the folder**
   (including the hidden `.github` folder, `android`, `www`, `package.json`, `package-lock.json`, `capacitor.config.json`, `native-entry.js`).
   Click **Commit changes**.
   Tip: if the hidden `.github` folder will not drag in, use **Add file > Create new file**, type `.github/workflows/build-apk.yml`
   as the name and paste the contents of that file.
3. Click the **Actions** tab. The "Build Pipeline OS APK" run starts by itself (first run: click "I understand my workflows, enable them" if asked).
4. When the run shows a green tick (about 4-6 minutes) open it and download **Pipeline-OS-apk** from the Artifacts section. Unzip it to get `app-release.apk`.
5. Send `app-release.apk` to the Samsung A07 (WhatsApp to yourself, Google Drive, or USB). Tap it, allow **Install unknown apps** for that app when Android asks, then Install.
6. Open Pipeline OS, tap **Allow** on the notification prompt, then More > Send test.
7. Samsung only: Settings > Apps > Pipeline OS > Battery > **Unrestricted**, so the 5 daily reminders arrive on time.

## Updating later
Edit `www/index.html`, upload it to the same repo, and the Actions tab builds a new APK.
Every build is signed with the same key, so the new APK installs over the old one and keeps all data.

## Before you sell it on Whop
- In `www/index.html` find `const DEF={` and empty `co1:` and `co2:` (your two checkout links). Otherwise every buyer's scripts will send YOUR checkout link. Buyers then paste their own in More > Settings.
- `android/app/pipelineos.keystore` is your signing key. Keep the repo private and keep a backup copy.
- Reminders use the `USE_EXACT_ALARM` permission. It is fine for sideloaded APKs. Google Play would need it removed.
