Develop a simple "Hello World" Android application demonstrating project creation, Android
Studio interface, Android components, AVD creation, and application execution.
Project 1: Hello World
Project Name: HelloWorld
Template: Empty Views Activity
Project Architecture:
Total 5 files
I
Filename: MainActivity.java
package com.example.helloworld;
 import android.os.Bundle;
 import androidx.appcompat.app.AppCompatActivity;
 public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 }
 }
Path: app>java>com.example.helloworld>MainActivity.java
II
Filename: activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:orientation="vertical"
 android:gravity="center"
 android:padding="16dp">
 <TextView
 android:id="@+id/text_hello"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Hello, World!"
 android:textSize="24sp"
 android:textStyle="bold"
 android:textColor="#000000" />
</LinearLayout>
Path: app>res>layout>activity_main.xml
III
Filename: AndroidManifest.xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
 package="com.example.helloworld">
 <application
 android:allowBackup="true"
 android:icon="@mipmap/ic_launcher"
 android:label="@string/app_name"
 android:roundIcon="@mipmap/ic_launcher_round"
 android:supportsRtl="true"
 android:theme="@style/Theme.Helloworld">
 <activity android:name=".MainActivity"
 android:exported="true"> <!-- Added android:exported attribute -->
 <intent-filter>
 <action android:name="android.intent.action.MAIN" />
 <category android:name="android.intent.category.LAUNCHER" />
 </intent-filter>
 </activity>
 </application>
</manifest>
Path: app>manifest>AndroidManifest.xml
IV
Filename: colors.xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
 <color name="black">#FF000000</color>
 <color name="white">#FFFFFFFF</color>
 <color name="purple_500">#6200EE</color>
 <color name="purple_700">#3700B3</color>
</resources>
Path: app>res>values>colors.xml
V
Filename: styles.xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
 <style name="Theme.Helloworld"
parent="Theme.MaterialComponents.DayNight.DarkActionBar">
 <!-- Customize your theme here -->
 <item name="colorPrimary">@color/purple_500</item>
 <item name="colorPrimaryVariant">@color/purple_700</item>
 <item name="colorOnPrimary">@color/white</item>
 </style>
</resources>
Path: app>res>values>styles.xml
VI (Prebuild Project Code: To ensure proper project detail: No need to update until needed)
Filename: build.gradle.kts (Module:app)
plugins {
 alias(libs.plugins.android.application)
 }
 android {
 namespace = "com.example.helloworld"
 compileSdk = 35
 defaultConfig {
 applicationId = "com.example.helloworld"
 minSdk = 24
 targetSdk = 35
 versionCode = 1
 versionName = "1.0"
 testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
 }
 buildTypes {
 release {
 isMinifyEnabled = false
 proguardFiles(
 getDefaultProguardFile("proguard-android-optimize.txt"),
 "proguard-rules.pro"
 )
 }
 }
 compileOptions {
 sourceCompatibility = JavaVersion.VERSION_11
 targetCompatibility = JavaVersion.VERSION_11
 }
 }
 dependencies {
 implementation(libs.appcompat)
 implementation(libs.material)
 implementation(libs.activity)
 implementation(libs.constraintlayout)
 testImplementation(libs.junit)
 androidTestImplementation(libs.ext.junit)
 androidTestImplementation(libs.espresso.core)
 }
Path: Gradle Scripts > build.gradle.kts
Above the Android Studio near Main Menu Click the Play button to Run the Program
Recommended compulsory AVD Emulator: Pixel 4 API 25 with version 7.1.1 Nouga
