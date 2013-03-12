---
layout: post
title: "Southend Transport Project"
description: "OSA+YoHa Project"
category: project
tags: []
published: false
---

{% include JB/setup %}

Our initial aim from a technical perspective is to create a device that could possible consist of a combination of the following sensors.

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
Despite some reservations about the aesthetics and politics surrounding these devices they already contains the majority of these sensors out of the box.

### Scripting Language for Android (S4LA)

**Rooting a Nexus 7**

- Installing Android SDK for linux (makes adb cli tools available).
  <http://android.stackexchange.com/questions/37760/how-do-i-root-my-nexus-7>.
  *Note: Step 6 missing link [available here](http://teamw.in/project/twrp2/103)*
- Installing Android SDK for linux (makes adb cli tools available)
<http://bernaerts.dyndns.org/linux/245-ubuntu-precise-install-android-sdk>

**Get Scripting**

- SL4A - Scripting platform for Android. Allows access to native Android functions using Python, Perl, JavaScript, etc. <http://code.google.com/p/android-scripting/>
- Very quickly get a Python script running on Android including an installer and .apk file. <http://clusterbleep.net/blog/2012/07/31/how-to-create-an-android-app-and-apk-on-android-with-python/>

### PhoneGap + PhoneGap Plugins (native Android code)

**Planning on using PhoneGap as master application and polyfilling missing functionality (currently: camera timelapse & light sensor) with native Android code in PhoneGap Plugin** 