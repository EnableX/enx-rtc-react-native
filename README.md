# EnableX Click2Call Application: Simplify Voice Communication with Dialer SDK for Real-Time Calls

## Getting started

## Prerequisites:

1. Install [node.js](https://nodejs.org/)

2. Install and update [Xcode](https://developer.apple.com/xcode/) (you will need a Mac)
* React Native iOS installation [instructions](https://reactnative.dev/docs/environment-setup)

3. Install and update [Android Studio](https://developer.android.com/studio/index.html)
* React Native Android installation [instructions](https://reactnative.dev/docs/environment-setup)

## Installation:

`$ npm install enx-rtc-react-native --save`

### Mostly automatic installation

`$ react-native link enx-rtc-react-native`


#### IOS Installation
**Note:** Please make sure to have [CocoaPods](https://cocoapods.org/) on your computer.
If you've installed this package before, you may need to edit your `Podfile` and project structure because the installation process has changed.
1. In your terminal, change into the `ios` directory of your React Native project.

2. Create a pod file by running: `pod init`.

3. Add the following to your pod file:

```
target '<YourProjectName>' do

# Pods for <YourProject>
pod 'EnxRTCiOS'
pod 'Socket.IO-Client-Swift', '~> 15.0.0'
end

```
4. In case if you want Autolinking then don't do step 3. Add following in podfile:
      ...
      pod 'enx-rtc-react-native', :path => '../node_modules/enx-rtc-react-native/ios/RNEnxRtc.podspec'
      ...
      
5. Now run, `pod install`

6. After installing the EnxRTCiOS  SDK, change into your root directory of your project.

7. Now run, `react-native link enx-rtc-react-native`.

8. Open `<YourProjectName>.xcworkspace` contents in XCode. This file can be found in the `ios` folder of your React Native project. 

9. Click `File` and `New File`

10. Add an empty swift file to your project:
* You can name this file anything i.e: `EnxInstall.swift`. This is done to set some flags in XCode so the Swift code can be used.

11. Click `Create Bridging Header` when you're prompted with the following modal: `Would you like to configure an Objective-C bridging header?`

12. Ensure you have enabled both camera and microphone usage by adding the following entries to your `Info.plist` file:

```
<key>NSCameraUsageDescription</key>
<string>Your message to user when the camera is accessed for the first time</string>
<key>NSMicrophoneUsageDescription</key>
<string>Your message to user when the microphone is accessed for the first time</string>
```

If you try to archive the app and it fails, please do the following:

1. Go to Target
2. Click on Build Phases
3. Under the Link Binary With Libraries section, remove the libEnx.a and add it again 


#### Android Installation

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.rnenxrtc.EnxRtcPackage;` to the imports at the top of the file
  - Add `new EnxRtcPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':enx-rtc-react-native'
  	project(':enx-rtc-react-native').projectDir = new File(rootProject.projectDir, 	'../node_modules/enx-rtc-react-native/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':enx-rtc-react-native')
  	```
4. Add following permisions in Android Manifest file:

        <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
        <uses-permission android:name="android.permission.CAMERA" />
        <uses-permission android:name="android.permission.CHANGE_NETWORK_STATE" />
        <uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />
        <uses-permission android:name="android.permission.RECORD_AUDIO" />
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
        <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
        <uses-permission android:name="android.permission.BLUETOOTH" />
        <uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
		
## Usage
```javascript
import Enx from 'enx-rtc-react-native';

// TODO: What to do with the module?
Enx;
```
 ## Extra Notes 
 Check ExtraNotes file in case of any issue.
 
 ## Trial 
 Try a quick Video Call: https://try.enablex.io/ <br/>
Sign up for a free trial https://www.enablex.io/free-trial/

