# Game Lingo for Android TV / Google TV 1.1.0 (30)

Corresponding source for the dedicated TV build of com.mustafasenocak.gamelingo.
Copyright (C) 2026 Mustafa SENOCAK. Game Lingo-owned code is distributed under
LICENSE-Android (GNU AGPL 3.0 or later, with the included additional permissions).
Third-party code retains its own license. ZXing 3.5.4 source is included under
Apache-2.0. No credentials, signing keys, user data, backend or admin code is included.

The TV receiver shares its native source and brand assets with the Game Lingo
phone project. It displays captions received from a paired phone over pinned TLS.
The television build contains no camera OCR, payment SDK, PS5 connection engine,
Flutter runtime, translation service credentials or speech engine.

## Build

Use Android SDK 36, Java 17 or newer and Gradle 9.1.0 (the wrapper is included).
The build pins Android Gradle Plugin 9.0.1 and ZXing 3.5.4. Set ANDROID_HOME to
your Android SDK. All output stays in build/android-tv on the project disk.
Create android/key.properties using your own upload signing key:

    storeFile=/absolute/path/to/your/upload-keystore.jks
    storePassword=YOUR_PASSWORD
    keyAlias=YOUR_ALIAS
    keyPassword=YOUR_PASSWORD

Then run from the project root:

    ./android/gradlew -p android-tv :app:bundleRelease :app:lintRelease

To create an independently signed debug installation, keep your own signing
configuration file and run :app:assembleDebug. The owner's signing key and
Google Play signing key are deliberately not included. Source and build rights
do not require a Game Lingo Premium subscription.

## Use

Install Game Lingo on the phone and a compatible Android/Google TV. Put both on
the same LAN. Use the five-step TV guide, allow display over other apps, and scan
the television pairing QR in the phone app. The pairing QR expires after five
minutes and is never included in this source package. After pairing, select the
console's HDMI input. Captions and speech are generated on the phone; the TV
only displays captions. HDMI overlay support depends on the television model.
The user can stop the receiver on the TV or disconnect from the phone, and a
session expires after two hours. The app never pairs with other TVs automatically.

The Android phone PS5 implementation is not included in this TV source release.
This archive corresponds only to the dedicated television binary.

Download [GameLingo-TV-1.1.0-30-source.zip](GameLingo-TV-1.1.0-30-source.zip).
The archive contains SOURCE-MANIFEST.json and all TV client build inputs.
See [SHA256SUMS](SHA256SUMS) to verify the download.
