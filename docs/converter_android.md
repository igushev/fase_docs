# Create Android Application
  * Download `fase_android` repository from [here](https://github.com/igushev/fase_android);
  * Delete directories `.idea`, `app/build`;
  * Launch Android Studio;
  
  * Go to *fase_android/app/src/main/AndroidManifest.xml*;
  * Select manifest->package and go to Refactor->rename and rename from *com.fase* to *com.converter*;
<img alt='Android Studio AndroidManifest' src='../images/converter_android/android_studio_android_manifest.png'>
  
  * Go to *fase_android/app/build.gradle*;
  * Rename *android->defaultConfig->applicationId* from *com.fase* to *com.converter*;
  * Update server URL in *android->buildTypes->debug->API_HOST* and *android->buildTypes->release->API_HOST* to
  `http://converterfase-env-prod.us-west-2.elasticbeanstalk.com/`
  * Update *google_maps_api_key* if your Application uses signing up with home city selection and/or Place picker;
<img alt='Android Studio build.gradle URL' src='../images/converter_android/android_studio_build_gradle_url.png'>
  
  * Go to *fase_android/app/google-services.json*;
  * Rename both *package_name* from *com.fase* to *com.converter*;
<img alt='Android Studio google-services.json' src='../images/converter_android/android_studio_google_services.png'>

  **NOTE.** Properly when project is created in Firebase *fase_android/app/google-services.json* must be downloaded from
  Firebase Console.

  * Go to *fase_android/app/src/main/res/values/strings.xml*;
  * Rename app_name from *Fase* to *Converter*;
  
  * Go to *res->new->Image Asset* and add icons;

  * Click *Build->Build APK(s)*
  
You can download APK file to an Android Phone, install the application and run:
 <img alt='Converter Android Launch' src='../images/converter_android/converter_android_launch.png'>