# Remote Picker fork

This maintained fork adds an on-TV picker for the remote TV button. It is separate from upstream's
small launcher core. Maintainer: [lionlev21](https://github.com/lionlev21).

Use the `tv-button-picker` branch. Build: `cd launcher && ./gradlew testReleaseUnitTest lintRelease assembleRelease`.
Use JDK 17 and Android SDK 34. Install your built APK using ADB; preserve the application ID and signing
key to update an existing installation without clearing its settings. Back up configuration first.

Open Launcher settings, TV button. Choose Follow configuration, Input switcher, Live TV, or an app.
Enable the existing Input button or Home button accessibility helper when prompted. No new service,
network permission or telemetry is added. Follow configuration preserves app_keys; explicit TV choices
change only that key and are stored outside theme preferences. Cancelled/repeated keys are handled.
The chooser has app names only, locale sorting, D-pad focus and Hebrew RTL layout.
English/Hebrew settings strings are included; other locales fall back to English for these new strings.

Real Android TV hardware validation covered the physical TV key from Home and another app, and
Hebrew chooser navigation. Device model/configuration remain private. Latest upstream refresh is built, linted and unit-tested; original physical tests do not claim coverage of every remote or firmware.

This fork deliberately excludes the optional Shizuku integration and capacity totals; those are
separate add-on proposals. For upstream fixes use the original project's issue tracker; for this
picker [open an issue on the fork](https://github.com/lionlev21/cleanyourtv/issues).
