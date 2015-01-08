# cordova-telephony-not-required
Extremely simple plugin that simply sets hardware telephony as not required on Android.

# Usage

    cordova plugin add https://github.com/app-sauce/cordova-telephony-not-required.git

# Result

The following is added to the AndroidManifest.xml

    <uses-feature android:name="android.hardware.telephony" android:required="false" />

# Why, Oh Why?

Phonegap build [has a way](issue-355) add properties in the config.xml, but [Cordova](cordova) can
only do that via a plugin. Unfortunately, Cordova plugins enable Android permissions that have
[required-feature side effects](perms). The result is that your app won't be available on devices
without that hardware--even if you have code that handles the missing hardware.

[cordova]: http://cordova.apache.org/
[issue-355]: https://github.com/phonegap/build/issues/355
[perms]: http://developer.android.com/guide/topics/manifest/uses-feature-element.html#permissions
