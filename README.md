# Planar Infinity releases

Signed release builds of the Planar Infinity tablet app.

The app's **Upgrade** menu item reads `index.html` here, compares the linked
version with the one it is running, and downloads the newer APK.

- APKs are named `PlanarInfinity<VersionName>.apk`, where `<VersionName>` is
  the app's `version_name` string with the spaces removed
  (for example `Nov23 BluetoothPermissions` → `PlanarInfinityNov23BluetoothPermissions.apk`).
- The first `<a href>` in `index.html` must point at the newest APK by its full
  URL. Keep `index.html` well-formed XML; the app parses it with an XML parser.

To install by hand, download the newest APK on the tablet and open it.
