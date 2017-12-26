How to install AndroidAPS
=========================

Install Android Studio
----------------------

Look here: [Installing Android Studio](https://developer.android.com/studio/install.html)

Building APK
============

* Download the ![AndroidAPS repository](https://github.com/MilosKozak/AndroidAPS) and extract the files.

* Run Android Studio and select 'Open an existing Android Studio project', selecting the location of the extracted files.

* Click on BuildVariants button on the bottom left of the Android Studio, and notice that you have several kinds of build types.


![fullWearcontrolRelease](https://github.com/gempickfordwaugh/AndroidAPS/raw/b09d7dc444f59b799888bcd596e36e1d562a9674/fullwearcontrolrelease.png)

* Select the build type you want to build. There are different modular options, the different parts of the name are described below to help you choose, we recommend **bold** for default AndroidAPS app (**fullWearcontrolRelease**) or _italic_ for parents monitoring looping (_nsclientWearRelease_).
    * **full - full app**
    * _nsclient - downloads treatments from NS and uploads care portal entries (no looping, just monitors looping from elsewhere)_
    * openloop - just the OpenAPS part of the app (no pump driver)
    * pumpcontrol - just the DanaR remote control part of the app (no looping function, just for bolusing)<br><br>

    * Nowear - just phone app, doesn't include watch app
    * _Wear - includes android wear watch app for viewing_
    * **Wearcontrol - includes android wear watch app for controlling pump (e.g. temp targets and bolusing)**<br><br>

    * _**Release - should be the default choice**_
    * Debug - just for people coding

* Go to Build Menu and click on Generate Signed APK

* Set a keystore and password, if this is your first time then Create new, or fill in the details of your existing one.  For more information about using the keystore see [https://developer.android.com/studio/publish/app-signing.html#generate-key](https://developer.android.com/studio/publish/app-signing.html#generate-key)

![Generate signed APK](https://github.com/gempickfordwaugh/AndroidAPS/raw/b09d7dc444f59b799888bcd596e36e1d562a9674/generate%20signed%20APK.png)

*   Select the same build type as previous, select V1 (Jar Signature) and click Finish. 

![Select build type](https://github.com/gempickfordwaugh/AndroidAPS/raw/b09d7dc444f59b799888bcd596e36e1d562a9674/generate%20signed%20APK%20select%20buildtype%20v1.png)

* Please wait for some time until the APK is created. You will get the pop-up below when the process is done.

![Generating APK](../images/androidstudio3.png)

* Click on 'Show in Explorer'. You'll find the APK is generated, sometimes it may take time to display.

* Copy the APK with the same finename as the buildtype you chose to your android phone, and install it.  
  If the apk does not install and you have an older version of AndroidAPS on your phone that was signed with a different key then you will need to uninstall this first, remember to export your settings if so.
  
Update to a new version
=======================
  
Install git (if you don't have it)
----------------------------------
* Any git version should work. For example https://git-scm.com/download/win
* Let Studio know where is git.exe located: File - Settings - Version Control - Git
![Git](../images/git.png)

Selecting a branch
------------------

* If you want to change branch select another branch from tray: master (latest release) or dev (developement version)

![Branch in tray](../images/branchintray.png)

and then checkout

![Checkout](../images/checkout.png)

Updating branch from Github
---------------------------

* Press Ctrl+T, select Merge method and press OK

![Merge](../images/merge.png)

On the tray you'll see green message about updated project

Upload to phone
---------------

* Connect phone now
* Press "Play" button on top toolbar

![Play](../images/play.png)

* Select connected phone and press OK

![Connected phone](../images/connectedphone.png)