# CleanYourTV Toan Nguyen — Android TV Launcher with Home Cards

A free Android TV / Google TV launcher with **two live info cards right on Home**: local weather and the Vietnamese lunar calendar.

This build is based on [CleanYourTV](https://github.com/Gathin23/cleanyourtv) (MIT) — a lightweight, debloat-friendly launcher — with Home info cards added on top.

> **One difference from upstream:** this build requests the `INTERNET` permission so the weather card can fetch data. Upstream CleanYourTV deliberately has no network access. The weather card only contacts two free, no-account services — Open-Meteo for weather and ipwho.is / ip-api.com for IP geolocation — and sends nothing else anywhere.

## What you see on Home

- **Weather card** — current temperature, condition, humidity and AQI for the TV's location (detected automatically, no setup). Refreshes every 30 minutes and keeps the last readings when offline.
- **Lunar card** — Vietnamese lunar date (day/month, month + Can Chi year) and the countdown to Tết, computed on the TV in Vietnam time. No network needed.
- The cards sit under the clock and slide away when you scroll down to your apps, so they never cover the app grid. A theme can turn them off with `"home_cards": false`.

Also included from the base launcher: lunar date in the header, Kids Lock with a time-based PIN, module cards, custom themes and wallpapers, and a clean app grid and dock.

## Install

On your Android TV / Google TV (Android 8.0+):

1. **Downloader (easiest):** install the free Downloader app from the Play Store, open it, type the code from the release post, press Go, then Install.
2. **Send Files to TV:** install the app on your TV and your phone, send the APK from your phone, open it with a file manager and Install.
3. **USB:** copy the APK to a FAT32 USB stick, plug it into the TV, open it with a file manager and Install.

Then press **Home**, pick this launcher and choose **Always** to make it your default Home screen.

Notes:

- If the original CleanYourTV launcher is already installed, uninstall it first — this build uses the same package name with a different signature, so it cannot install over it. (Uninstalling the original also removes its theme and settings.)
- The first time you install an APK this way, the TV asks you to allow "Install unknown apps" for the app you install from — allow it once.
- To go back to your stock launcher later, set it as Home again in Settings → Apps → Default apps → Home app.

## Download

Get the APK from the [latest release](https://github.com/TheodoreNguyenSa/cleanyourtv-toan/releases/latest).

## Changelog

### v2.7.2

- Fixes the crash when scrolling the app grid: the manual build did not package core-ktx, so `RecyclerView` recycling a view holder hit a missing `androidx.core.view.ViewKt` class and the launcher died (the app underneath then showed through).
- APK: `CleanYourTV-ToanNguyen-v2.7.2.apk` — 1,957,200 bytes, SHA-256 `1570c188e701c5bda1ca9a8b2973f9df1db3c06ceed71fdbeefd4ed4f5cd744d`, versionCode 14. Downloader code: 9805111.

### v2.7.1

- About screen now shows a website QR + link (`toannguyeninoz.pp.ua`) next to Buy Me a Coffee.
- APK: `CleanYourTV-ToanNguyen-v2.7.1.apk` — 1,908,048 bytes, SHA-256 `f4c2f85b587246c45544c5099da9beef6719316a2a749c8ddd8ce589af43b0c9`, versionCode 13. Downloader code: 4163643.

### v2.7

- New **Tùy biến** (Customise) screen in Settings: language (system / Vietnamese / English), info-card toggles (weather and lunar separately), card order, lunar date on top, weather city (Adelaide, Melbourne, Sydney, Brisbane, Perth, Canberra, Hobart, Darwin), 5 accent colours, background themes (Dark / Light / Blue / Green), frosted or solid dock, app names under tiles, 12/24-hour clock, wallpaper dim, hide apps, pin favourite apps, sort A–Z or recently used, screensaver delay, and a PIN lock for Tùy biến (PIN theo giờ — the same dynamic PIN as Kids Lock). "Khôi phục theo theme" clears all on-TV choices back to the theme. Every new default matches current behaviour.
- New **Giới thiệu & Ủng hộ** (About) screen: version, author, GitHub link, **Kiểm tra cập nhật** (checks the GitHub releases, downloads and installs an update), credits, Buy Me A Coffee and PayPal, a share card with the Downloader QR code (1238220), "Mới trong v2.7", and **Sao lưu / Khôi phục cài đặt**.
- All 24 missing Vietnamese strings translated (EN 150 → 229 strings, VI 126 → 228; `date_format_home` stays English-only by design — it is a reference marked `translatable="false"`).
- APK: `CleanYourTV-ToanNguyen-v2.7.apk` — 1,903,870 bytes, SHA-256 `02b31a6bc6b8afbde5af9b7ee6a43a2e579086b183936dcf94a24e2c3d6bde57`, versionCode 12. Downloader code: 1111249.

### v2.6-toan4

- New **Close apps** button in the top row (between Kids and Settings): one press clears background apps and their caches to free memory. Core system apps are never touched, and streaming apps (YouTube TV, Netflix) are skipped — note Android will not force-close an app that is currently playing media or showing a picture-in-picture window.

### v2.6-toan3

- Added the two Home info cards: live weather (Open-Meteo, auto location) and Vietnamese lunar calendar (Tết countdown, Vietnam time).
- Cards hide while you scroll the app grid and return when you scroll back to the top.
- `home_cards` switch in `config.xml` (on by default; a theme can set it to `false`).

## Support

Made by Toan Nguyen In Oz — free for the Vietnamese community in Australia and everywhere.

- ☕ Buy me a coffee: https://buymeacoffee.com/toannguyeninoz
- 💛 PayPal (direct): https://www.paypal.me/ToanNguyen189

## Credits

- Launcher base: [CleanYourTV](https://github.com/Gathin23/cleanyourtv) by Gathin23 (MIT).
- Lunar calendar math: astronomical algorithm by Hồ Ngọc Đức.
