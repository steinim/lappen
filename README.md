#Lappen

ABCD for hjerte- og lungeredning

## Release

### Android

Top of `config.xml` should look like this:

```
<widget android-versionCode="100000" id="no.hkraft.lappen" version="0.0.1" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
```

* Up `android-versionCode` with 1
* Set correct `version`

```
ionic cordova build --release android
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore release-key.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk Lappen
~/Library/Android/sdk/build-tools/28.0.3/zipalign -v 4 ./platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk Lappen_<version>.apk
```

Go to https://play.google.com/apps/publish/ to publish.

### iOS

Top of `config.xml` should look like this:

```
<widget android-versionCode="100000" id="no.hkraft.lappen.Lappen" version="0.0.1" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
```

* Set correct `version`

```
ionic cordova build --release ios
open platforms/ios/Lappen.xcworkspace
```

Go to https://itunesconnect.apple.com to publish.
