---
published: "true"
layout: post
title: Southend Transport Project
description: OSA+YoHa Project
category: project
tags: []

---

{% include JB/setup %}

Our initial aim from a technical perspective is to create a device that could consist of a combination of the following sensors.

- Light
- Sound level (db)
- Vibration
- 3D movement (accelerometer)
- Pothole detection (pressure sensor, or tilt sensor, or custom built springy switch)
- Traffic counting
- Face/person detection.
- Body: GSR, heart rate, heart rate variability,  
- GPS detection.
- Video/Stills camera.

## Android device
Despite some reservations about the aesthetics and politics surrounding these devices they already contain the majority of these sensors out of the box.

### Scripting Language for Android (S4LA)
Combined we have more experience in Python, Perl, JavaScript so are attempting to use this alpha(!) software that enables scripting languages (Python in this case) to be installed on rooted Android device.

####Rooting a Nexus 7

* Installing Android SDK for linux (makes adb cli tools available).
  <http://android.stackexchange.com/questions/37760/how-do-i-root-my-nexus-7>.  
  *Note: Step 6 missing link [available here](http://teamw.in/project/twrp2/103).*
* Installing Android SDK for linux (makes adb cli tools available)  
<http://bernaerts.dyndns.org/linux/245-ubuntu-precise-install-android-sdk>

####Get Scripting

* SL4A - Scripting platform for Android. Allows access to native Android functions using Python, Perl, JavaScript, etc.  
<http://code.googlecom/p/android-scripting/>
* Very quickly get a Python script running on Android including an installer and .apk file.  
<http://clusterbleep.net/blog/2012/07/31/how-to-create-an-android-app-and-apk-on-android-with-python/>

####Overview

* Very easy  to install and use (once device is rooted)
* Simple API. Two lines of code to access Camera, GPS sensors, etc
* Flakey. Camera gave Java NullPointer error and GPS returned empty results array
* Because of simple API and Java code used to access sensors, debugging is a problem.


### PhoneGap + PhoneGap Plugins (native Android/Java)

Planning on using PhoneGap as master application and polyfilling missing functionality (currently: camera timelapse & light sensor) with native Android code in PhoneGap Plugin.

####Native Development - Camera

- Android Camera Application demo <https://github.com/commonsguy/cw-advandroid>
- Stoping the screen from dimming <http://chris-allen-lane.com/2012/11/phonegap-prevent-an-android-devices-screen-from-sleeping/>

####PhoneGap Development
 
* *App*Laud Eclipse Plugin - PhoneGap project bootstrapping. <http://www.mobiledevelopersolutions.com/home/start>
* Adding native options menu to PhoneGap project. Used for stopping activity. <http://simonmacdonald.blogspot.co.uk/2012/11/building-native-menu-with-phonegap.html>
* Launching a new activity from PhoneGap Plugin with Intent - <http://smus.com/android-phonegap-plugins/>

###Sensors

####Potholes / Shake Detection

[Difficulties involved in detecting potholes](http://stackoverflow.com/questions/6502492/where-can-i-find-resources-and-code-samples-for-making-use-of-the-signal-from-an) because accelerometer does not detect shifts relative to previous position. Essentially works out 3 axis orientation. Despite this there are a lot of 'shake' detection solutions that use accelerometer such for Android and PhoneGap:
* PhoneGap shake events <http://mobile.tutsplus.com/tutorials/phonegap/phonegap-from-scratch-device-apis/>
* Android Native shake events <http://stackoverflow.com/questions/2317428/android-i-want-to-shake-it>

####Light Sensor
* Light Sensor - Basic Java example <http://android-coding.blogspot.co.uk/2011/10/using-android-device-build-in-light.html>

###IOIO - Breakout Board for Android
Breakout board designed for use with Android phones and programmable in Java. We intend to use this to extend the available sensors available on the phone. For instance to incoporate Galvanic Skin Response sensors to measure bodily changes in accordance with the journey. Purchased from Sparkfun - <https://www.sparkfun.com/products/11343>  

####Docs
* Github documentation - <https://github.com/ytai/ioio/wiki>

####Resources
* Firmware - <https://github.com/ytai/ioio/tree/master/release/firmware/application>
* Client software, udev rules & examples - <https://github.com/ytai/ioio/wiki/Downloads>
* IOIODude (for flashing firmware) - <https://github.com/ytai/ioio/wiki/IOIO-OTG-Bootloader-and-IOIODude>
* Comprehensive list of examples - <https://github.com/ytai/ioio/blob/master/software/applications/IOIOSimpleApp/src/ioio/examples>
