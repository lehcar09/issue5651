# Issue 5651
### Github Issue Link
[- https://github.com/firebase/firebase-android-sdk/issues/5644](https://github.com/firebase/firebase-android-sdk/issues/5651)

### Summary
Build product flavors always uses the last configured "serviceCredentialsFile"

  
### Prerequisite:
- add `google-services.json` file in app
- add service accounts in credential folder

### Steps to reproduce
Run command `./gradlew assembleDebug appDistributionUploadDemoDebug` 

#### Actual Logs
```
Task :app:appDistributionUploadDemoDebug
Using APK path in the outputs directory: <project-path>/Issue5651/app/build/outputs/apk/demo/debug/app-demo-debug.apk.
Uploading APK to Firebase App Distribution...
Using service credentials file specified by the serviceCredentialsFile property in your app's build.gradle file: <project-path>/Issue5651/credential/service_account2.json
Uploading the APK.
```

#### Expected Logs
```
Task :app:appDistributionUploadDemoDebug
Using APK path in the outputs directory: <project-path>/Issue5651/app/build/outputs/apk/demo/debug/app-demo-debug.apk.
Uploading APK to Firebase App Distribution...
Using service credentials file specified by the serviceCredentialsFile property in your app's build.gradle file: <project-path>/Issue5651/credential/service_account.json
Uploading the APK.
```
