# Planar Infinity releases

Signed release builds of the Planar Infinity tablet app.

**Latest:** [release.v1.8.apk](https://raw.githubusercontent.com/madmattman/planar-infinity-releases/main/release.v1.8.apk), version 1.8

Earlier releases stay here too, so a tablet can go back to one.

## Installing

On the tablet, open the app's logo menu and tap **Upgrade**. Or download the
newest APK above on the tablet and open it.

Upgrade reads `index.html` in this repo and compares the version it links
with the version the tablet is running:

- **Newer** – downloads it straight away.
- **Same version** – asks "Reinstall version …?" and reinstalls if you confirm.
- **Older** – asks "Install older version …?" and installs it if you confirm.

Older builds – the ones whose logo menu shows a name such as
"Nov23 BluetoothPermissions" instead of a version number – still check
zeroplayer.com, so install the latest release on those tablets by hand once.

## How releases are named

Each APK is `release.v<versionName>.apk`, where `versionName` comes from
`PlanarInfinity/app/build.gradle` in the app's source repo – for example
`release.v1.6.apk`, then `release.v1.7.apk`. Versions compare part by part,
so 1.10 is newer than 1.9.

`index.html` must link the newest APK by its full URL in its **first**
`<a href>`, and stay well-formed XML, because the app parses it with an XML
parser.

## Publishing

`rake deploy`, run in the app's source repo, publishes a release here: it
raises `versionName` (1.6 → 1.7), builds and signs the APK, writes it and
`index.html` into a checkout of this repo, then commits and pushes. See the
Rakefile for the `SAME_VERSION`, `FEATURES`, `RELEASES_DIR` and `KEYSTORE`
options.

The app's `versionCode` stays at 16 on purpose: the app's database schema
depends on it.
