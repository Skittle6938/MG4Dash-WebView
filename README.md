# MG4Dash WebView

Hosts the recent web engine that MG4Dash can install on the MG4 head unit (Settings > Update > Recent web engine).

The car's own WebView is Chromium 66 (2018), which cannot run most of today's map sites. MG4Dash downloads the file
below from this repository's release, checks its SHA-256 and installs it as an update of the system WebView
(`com.android.webview`). "Restore the original engine" in MG4Dash removes the update and Chromium 66 comes back.

| Release asset | Version | Size | SHA-256 |
|---|---|---|---|
| `webview-138.0.7204.63-aosp-testkey.apk` | Chromium 138.0.7204.63 (`com.android.webview`, versionCode 720406301, minSdk 26, arm64-v8a + armeabi-v7a) | 243562802 bytes | `d057f4921330fe59853eb79a9f4d4e9f980c1c0cf65651dbfbd9bf09f0b59c3c` |

## Source

LineageOS's prebuilt Chromium WebView for arm64:
[LineageOS/android_external_chromium-webview_prebuilt_arm64](https://github.com/LineageOS/android_external_chromium-webview_prebuilt_arm64)
at commit `f6f994f9912b26d1dffd100f6de959f9dfd31414` ("Update Chromium Webview arm64 to 138.0.7204.63"), file
`webview.apk` (243509357 bytes, SHA-256 `446ead71292578830d99e690fd8dded73bc63d85df80f0cfba37762ccb330326`).
Chromium 138 is the last version that supports Android 9.

Its content is unchanged. It was only zipaligned and re-signed (APK signature v1 + v2) with AOSP's public test key
(`build/target/product/security/testkey`, certificate SHA-256
`a40da80a59d170caa950cf15c18c454d47a39b26989d8b640ecd745ba71bf5dc`), the key of the MG4's own WebView, so that it
installs as an update of it.

## License

Chromium is distributed under the BSD license and the licenses of its third-party components; see
[chromium.googlesource.com/chromium/src/+/main/LICENSE](https://chromium.googlesource.com/chromium/src/+/main/LICENSE)
and the credits included in the APK (`about:credits`).
