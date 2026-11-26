# Palakpakan Meter — Sukatan ng Hiyawan at Palakpakan

Pinoy fiesta-style decibel meter for judging contests (cheering, applause, yell contests). Uses the phone's microphone.

- 0–4 volume-level chart (Tahimik → Pang-Fiesta!), plus a 💡 Neon lights-only mode
- Contestant list, timed rounds with countdown, scoring by **Pinakamalakas** (peak) or **Karaniwan** (average), automatic ranking
- 🏆 winner screen with podium and confetti; 📱 in-app QR code for sharing the app
- Screen stays on and the app runs full screen

**Download:** scan `qr-card.html`, or open https://github.com/gnotesamsung7-hue/palakpakan/releases/latest/download/PalakpakanMeter.apk

## Folders
- `www/` – the app (single page). Version number: `APP_VERSION` in `www/index.html`
- `android/` – Android project (Capacitor 7). Adds the microphone permission, keep-screen-on and full screen
- `qr-card.html` – printable QR card that always points to the latest APK
- `.github/workflows/main.yml` – builds the signed APK on every push and publishes it to Releases

## One-time setup
1. **Signing key secrets** – repo → **Settings → Secrets and variables → Actions → New repository secret**. Add the 4 secrets from `github-secrets-palakpakan.txt` (`ANDROID_KEYSTORE_BASE64`, `ANDROID_KEYSTORE_PASSWORD`, `ANDROID_KEY_ALIAS`, `ANDROID_KEY_PASSWORD`). Keep that file and `palakpakan-release.jks` backed up privately. Never upload them to the repo.
2. **Build** – **Actions → Build Palakpakan Meter APK → Run workflow** (or push any change). The APK appears under **Releases**, and the QR codes always point to the latest one.

## Notes
- The dB reading is an estimate (not a certified sound level meter). Comparisons are fair as long as the same phone stays in the same spot for every contestant. Use the Calibration slider to match a real meter.
- First launch asks for microphone permission – tap **Allow**.
