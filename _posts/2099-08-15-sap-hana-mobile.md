---
layout: post
title: "SAP-HANA Hybrid Mobile Development"
excerpt: "Cordova jQuery"
tags: [apple, mac, SAP-HANA, Mobile, Development, Cordova, jQuery]
image:
  feature: pic Giant-Swiss-Army-Knife-1900x500.jpg
  credit: 
  creditlink:
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

<a id="Setup_Github"></a>

This entry describes the setup of SAP HANA mobile development environment.

## Hybrid app?
A Hybrid app is like a native mobile app in that it's' installed from a store
and it is activated by clicking on an icon.
But that icon is pressed, the app actually runs within a browser. 

The advantage of this approach is that it's simpler to program.
Programmers work in JavaScript rather than the more complicated 
Java on Android and Objective-C or Swift on Apple devices.  


## Licensing for the Cloud
PROTIP: You'll' need a fast internet connection to program SAP HANA mobile. 

SAP HANA development is done using a web browser.

There are two different sets of cloud accounts:

A) The development platform runs in SAP's HANA cloud Platform (HCP)
mobile services accessed through the SAP HANA Cloud Portal.

   * HCP Mobile services (HCPms)
   * HANA Cloud Portal Services
   * SAP Web IDE ("sapwebide") subscription
   * Fiori Launch Pad

Get a Trial license of **SAP Mobile Platform SDK SP11** installer for your platform type.

http://help.sap.com/disclaimer?site=https://store.sap.com/sap/cp/ui/resources/store/html/SolutionDetails.html?pid=0000013098&catID=&pcntry=US&sap-language=EN&_cp_id=id-1409756206625-0

B) At http://sapmobilesecure.com
A 30-day license of SAP Mobile Secure (an MDM product) 

QUESTION: What is the cost of SAP cloud licenses. 


## Installation
Here are the steps to install the various libraries, which must be of specific versions:

0. Create a folder that will be under git protection. 

   On Macs I prefer a path such as ~/gits/user1/repo1.

   ### Corporate Proxy

0. Configure for corporate proxy. Create a hidden folder containing file config (no file extension):

   ```
   ~/.plugman/config
   ```

   contents:

   ```
proxy = http://proxy:8080
https-proxy = http://proxy:8080
   ```
## Git

## Node.js

0. Install Node.js 5.4.1 dated 2016-01-12

   * <a target="_blank" href="https://nodejs.org/en/download/releases/">Previous releases</a>

   * Select node-v5.4.1.pkg for Macs.

   * node -version

## Cordova

0. Download libraries:

   ```
   npm install -g cordova@5.2.0
   ```

   Do without sudo.

## SAP Kapsel

   SAP Mobile Platform Hybrid SDK (Kapsel).


## For iOS mobile

### XCode

## For Android mobile

### JDK 1.7+

### Android SDK 5.1.1 (API level 22)

0. Download SDK Tools only (not Android Studio) for Mac from

   http://developer.android.com/sdk/index.html#Other

0. Save file (for Mac, dmg)

0. Unzip to folder android-sdk-mac_x86.

0. 

If you are in an environment where network access is controlled by a proxy server, configure proxy settings: select the Preferences menu of Android SDK Manager.
Install the latest Android SDK Platform-tools and Android SDK Build-tools package.
Note
Additionally for Kapsel push plugin, install the following:
Android support repository

Google play services
Set the ANDROID_HOME system environment variable in the .bash_profile. For example:
export ANDROID_HOME=/Users/<yourusername>/android-sdk-macosx

Add the tools and platform-tools to your path. For example:
<%ANDROID_HOME%/tools>

<%ANDROID_HOME%/platform-tools>

Launch the Android Virtual Device Manager (AVD) and create an Android virtual device based on API level 19 to be used as your emulated device.


### Ant for Android builds

0. Download Apache Ant 1.8 or later:

   ```
http://help.sap.com/disclaimer?site=http://ant.apache.org
   ```

0. Unzip the package, and follow the instructions in the INSTALL file.

0. Add the unzipped Ant bin directory path to your PATH environment.

0. 


## Footnotes

https://help.hana.ondemand.com/webide_hat/frameset.htm?93a25210b383451487ae4c56ac938ac1.html


https://blog.rollout.io/2016/03/app-development-guide/
   From Noob to ninja




