Adding the Android Minermob miner SDK to your app

Add it in your root build.gradle at the end of repositories:
allprojects {
   repositories {
       ...
       maven { url 'https://jitpack.io' }
   }
}
Add the dependency 
android {
   …...
   defaultConfig {
       minSdkVersion 19
       ……..
   }
   compileOptions {
       targetCompatibility 1.8
       sourceCompatibility 1.8
   }
}
dependencies {
implementation 'com.github.minermob:android-miner-sdk:1.1.0'
}
In your AndroidManifest.xml file, add the permissions line in 
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.WAKE_LOCK" />



Initializing the SDK
In the onCreate() function 

Starting

@Override
protected void onCreate(Bundle savedInstanceState) {
…..
…..
Minermob.init(this,"Developer ID","App Key");
if (Minermob.startMining()){
   Log.d("Device status","Yes supported");
}else{
   // no mining ad showing
   Log.d("Device status","No supported");
}

}

Stopping
@Override
protected void onCreate(Bundle savedInstanceState) {
…..
…..
Minermob.init(this,"Developer ID","App Key");
Minermob.stopMining();

}

Test

@Override
protected void onCreate(Bundle savedInstanceState) {
…..
…..
Minermob.init(this,"Developer ID","App Key");
Minermob.test();

}
