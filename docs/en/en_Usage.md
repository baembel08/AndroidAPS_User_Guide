Objectives
==========

AndroidAPS has a series of Objectives that need to be completed to walk you through the features and settings of safe looping.  They ensure you have configured everything detailed in the sections above correctly, and that you understand what your system is doing and why so you can trust it.

If you are upgrading phones then you can export your settings to keep your progress through the objectives; in the three dots in the top right corner select _Export settings_, it will tell you which folder it has saved the file to.  On your new phone copy the file over to that location and then select _Import settings_.  Not only will your progress through the objectives be saved, but also your safety settings such as max bolus etc.  If you do not export and import your settings then you will need to start the objectives from the beginning again.  It is a good idea to back up your settings frequently just in case.
 
* **Objective 1:** Setting up visualization and monitoring, and analysing basals and ratios
  * Select the right blood glucose source for your setup.  See [BG Source](http://androidaps-user-guide.readthedocs.io/en/latest/en/en_Configuration.html#bg-source) for more information.
  * Select the right Pump in ConfigBuilder (select Virtual Pump if you are using a pump model with no AndroidAPS driver for open looping) to ensure your pump status can communicate with AndroidAPS.  If using DanaR pump then ensure you have followed [DanaR Insulin Pump](http://androidaps-user-guide.readthedocs.io/en/latest/en/en_Configuration.html#DanaR-Insulin-Pump) instructions to ensure the link between pump and AndroidAPS.
  * Follow instructions in [Nightscout](http://androidaps-user-guide.readthedocs.io/en/latest/en/en_Configuration.html#nightscout) page to ensure Nightscout can receive and display this data.
<br><br>_You may need to wait for the next blood glucose reading to arrive before AndroidAPS will recognise it._
 
* **Objective 2:** Starting on an open loop
  * Select Open Loop either from Preferences, or by pressing and holding the Loop button in top left of the home screen.
  * Work through the [Preferences](http://androidaps-user-guide.readthedocs.io/en/latest/en/en_Configuration.html#Preferences) to set up for you.
  * Manually enact at least 20 of the temporary basal rate suggestions over a period of 7 days; input them to your pump and confirm in AndroidAPS that you have accepted them.  Ensure this data shows in AndroidAPS and Nightscout.
 
* **Objective 3:** Understanding your open loop, including its temp basal recommendations
  * Start to understand the thinking behind the temp basal recommendations by looking at the [determine basal logic](https://openaps.readthedocs.io/en/latest/docs/While%20You%20Wait%20For%20Gear/Understand-determine-basal.html) and both the forecast line in AndroidAPS homescreen/Nightscout and the summary of outputs from the calculations in your OpenAPS tab.
  <br><br>_You will want to set your target higher than usual until you are confident in the calculations and settings.  The system allows a low target to be a minimum of 4 or maximum of 10, and a high target to be a minimum of 5 and maximum of 15.  A temporary target as a single value can be anywhere in the range of 4 to 15.  The target is the value that calculations are based on, and not the same as where you aim to keep your blood glucose values within.  If your target is very wide (say, 3 or more mmol wide), you will often find because blood glucose is eventually predicted to be somewhere in that wide range not many fluctuating temporary basal rates are suggested. You may want to experiment with adjusting your targets to be a closer together range (say, 1 or less mmol wide), and observe how the behavior of your system changes as a result.  You can view a wider range (green lines) on the graph for the values you aim to keep your blood glucose within by entering different values in Preference > Range for Visualisation._
  <br><br>_Stop here if you are open looping with a virtual pump - do not click Verify at the end of this objective._

* **Objective 4:** Starting to close the loop with Low Glucose Suspend
  * Select Closed Loop either from Preferences, or by pressing and holding the Open Loop button in the top left of the home screen.
  * Set your target range slightly higher than you usually aim for, just to be safe.
  * Watch  how temporary basals are active by viewing the blue basal text on the homescreen or the blue basal render on the homescreen graph.
  * Ensure your settings have supported AndroidAPS to avoid having to treat a low glucose over a period of 5 days.  If you are still having frequent or severe low glucose episodes then consider refining your DIA, basal, ISF and carb ratios.
<br><br>_The system will override your maxIOB settings to zero, which means if blood glucose is dropping it can reduce basal for you, but if blood glucose is rising then it will only increase basal if the IOB is negative (from a previous Low Glucose Suspend), otherwise basal rates will remain the same as your selected profile.  You may temporarily experience spikes following treated hypos without the ability to increase basal on the rebound._
 
* **Objective 5:** Tuning the closed loop, raising max IOB above 0 and gradually lowering BG targets
  * Raise your maxIOB above 0 over a period of 1 day, the default is recommended to be 2 but you should slowly work up to this until you know your settings work for you.
  * Once confident on how much IOB suits your looping patterns then reduce your targets to your desired level.
 
* **Objective 6:** Adjust basals and ratios if needed, and then enable auto-sens
  * You can use [autotune](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autotune.html) as a one off to check your basals remain accurate, or do a traditional basal test.
  * Enable [auto-sens](http://androidaps-user-guide.readthedocs.io/en/latest/en/en_Usage.html#open-aps-features) over a period of 7 days and watch the white line on the homescreen graph show how your sensitivity to insulin may be rising or falling as a result of exercise or hormones etc, and keep an eye in the OpenAPS report tab how AndroidAPS is adjusting the basals and/or targets accordingly.
<br><br>_Don’t forget to record your looping in [this form](http://bit.ly/nowlooping) logging AndroidAPS as your type of DIY loop software, if you have not already done so._
 
* **Objective 7:** Enabling additional features for daytime use, such as advanced meal assist
  * Now you should feel confident with how AndroidAPS works and what settings reflect your diabetes best, then over a period of 14 days you can try additional features that automate even more of the work for you.
  
Open-APS-features
=================
  
  Some of the features in AndroidAPS are from OpenAPS oref0 code so please refer to the OpenAPS docs for these:
* [Advanced Meal Assist (AMA)](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#advanced-meal-assist-or-ama) after you give yourself a meal bolus, the system can high-temp more quickly after a meal bolus IF you enter carbs reliably.  Turn it on in the Config tab, you will need to have completed Objective 7 to use this feature.
* [Autosens](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#auto-sensitivity-mode) analyze historical data on the go and make adjustments if it recognizes that you are reacting more sensitively (or conversely, more resistant) to insulin than usual.  Turn it on in the Preferences menu, you will need to have completed Objective 6 to use this feature.
* [Temporary Targets (Eating Soon and Activity Mode)](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#eating-soon-and-activity-mode-temporary-targets) Temporary or “temp” targets are ideal for when you want the loop to adjust to a different target level for a short period of time (temporarily) for example when you plan on eating or exercising.  You can set temp targets either by the TempT option on the watch, Temporary Target button on the Actions tab, or by pressing and holding the current target displayed on the home screen.  Temporary targets have a pre-defined duration so you don't need to remember to turn it back to usual.  The homepage will show the current target as blue is your usual target, and green if a temporary target.

Circadian Percentage Profile
============================

* To enable Circadian Percentage Profile go to the Config Builder and select Enabled and Visible
* In the Circadian Percentage Profile menu (CPP) enter your base profile.  This is the default that the pump reverts to when not looping.  This profile can be modified in two ways:
  * Timeshift - this moves everything round the clock by the number of hours entered.  So for example, when working night shifts change the number of hours to how much later/earlier you go to bed or wake up.
  * Percentage - this  applies the same percentage to all parameters. If you set it to 130% (meaning you are 30% more insulin resistant), it will up the basal rate by 30%. It will also lower the ISF and IC accordingly (divide by 1.3 in this example).  It will be sent to the pump and then be the default basal rate. The loop algorithm (open or closed) will continue to work on top of the selected percentage profile.  So for example separate percentage profiles can be set up for different stages of the hormone cycle.

Working with profiles 1.5
=========================

Since version 1.5 the logic of using profiles changed.

Up to version 1.46 once you change profile the changes are immediately applied. 

AAPS may still work this old fashioned way until you create first "Profile switch" event with zero duration (explained later). By doing this AAPS starts tracking history of profiles and every new profile change requires another "Profile switch" even when you change content of the profile in NS. Updated profile is pushed to AAPS immediately but you need to switch the same profile again (in NS or AAPS) to start using these changes.

Internaly AAPS creates snapshot of profile with start date and duration and is using it within selected period. Duration of zero means infinite. Such profile is valid until new "Profile switch".

If you use "Profile switch" with duration profile is switched back to previous valid "Profile switch"

If you use local AAPS profiles (CPP, Simple, Local) you have to press button there to apply these changes (it creates proper "Profile switch" event).

This mechanism allows much precise calculations to the past and track profile changes.

In closed loop mode is recommended to turn on automatic update of profile in pump (in settings).


Profil Free Peak 0ref
=====================

With the profile "Free Peak 0ref" for Fiasp, you can enter when the maximum duration of action will be reached.

The DIA is automatically set to 5 hours, if he himself was not specified higher in the profile.

The following explanation is in English, but the graphics are clear again.

http://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and-why-it-matters/

![DIA explanation from diabettech.com](https://i1.wp.com/www.diabettech.com/wp-content/uploads/2017/07/DIA-Clamp.jpg?w=892)
<small>(Source: diabettech.com)</small>

For many, there is practically no noticeable effect from the Fiasp after 3-4 hours, but still 0.0xx units available.

These may then be e.g. in sports, but still noticeable.

Therefore AndroidAPS uses minimum 5h as DIA.


SMS Commands
============

In your android phone setting go to Applications > AndroidAPS > Permissions and enable SMS

In AndroidAPS go to Preferences > SMS Communicator and enter the phone number(s) that you will allow SMS commands to come from and also enable 'Allow remote commands via SMS'

Send a SMS to the phone with AndroidAPS running from your approved phone number(s) using any of the commands below in **bold**, the phone will respond to confirm success of command or status requested.

*BG*

- Last BG: 5.6 4min ago, Delta: -0,2 mmol, IOB: 0.20U (Bolus: 0.10U Basal: 0.10U)

*LOOP STOP/DISABLE*

- Loop has been disabled

*LOOP START/ENABLE*

- Loop has been enabled

*LOOP STATUS*

- Loop is disabled
- Loop is enabled
- Suspended (10 min)

*LOOP SUSPEND 20*

- Loop suspended for 20 minutes

*LOOP RESUME*

- Loop resumed

*TREATMENTS REFRESH*

- TERATMENTS REFRESH 1 receivers

*NSCLIENT RESTART*

- NSCLIENT RESTART 1 receivers

*DANAR*

- Last conn: 1 minago Temp: 0.00U/h @11:38 5/30min IOB: 0.5U Reserv: 34U Batt: 100

*BASAL STOP/CANCEL*
- To stop temp basal reply with code EmF

*BASAL 0.3*

- To start basal 0.3U/h reply with code Swe
- Remote basal setting is not allowed (if remote commands not allowed)

*BOLUS 1.2*

- To deliver bolus 1.2U reply with code Rrt
- Remote bolus not allowed (_if within 15 min after last bolus command or remote commands not allowed_)

*CAL 5.6*

- To send calibration 5.6 reply with code Rrt
- Calibration sent (_if xDrip is installed. Accepting calibrations must be enabled in xDrip+_)

Tips and Tricks
===============

* The founding principle of closed looping is that your basal rate and carb ratio is accurate.  All recommendations assume that your basal needs are met and any peaks or troughs you're seeing are a result of other factors which therefore require some one off adjustments (exercise, stress etc).  The adjustments the closed loop can make for safety have been limited (see maximum allowed temporary basal rate in [OpenAPS Reference Design](https://openaps.org/reference-design/)), which means that you don't want to waste the allowed dosing on correcting a wrong underlying basal.   If for example you are frequently low temping on the approach of a meal then it is likely your basal needs adjusting.  You can use [autotune](https://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/autotune.html) to consider a large pool of data to suggest whether and how basals and/or ISF need to be adjusted, and also whether carb ratio needs to be changed.  Or you can test and set your basal the [old fashioned way](http://integrateddiabetes.com/basal-testing/).

* Looping can reduce the pump battery faster than normal use.  If you unexpectedly run low then the battery from the blood test kit or setter can be used.  It is best to change battery at 25% as communication becomes challenging then.  You can set warning alarms for pump battery by using the PUMP_WARN_BATT_P variable in your nightscout site.  Tricks to increase battery DANA life include:
  * reduce the length of time the LCD stays on (within DANA settings menu)
  * reduce the length of time the backlight stays on (within DANA settings menu)
  * select notification settings to a beep rather than vibrate (within DANA settings menu)
  * only press the buttons on the pump to reload, use AndroidAPS to view all history, battery level and reservoir volume.
  * clean battery terminals with alcohol wipe to ensure no manufacturing wax/grease remains
  * the DANA startup procedure draws a high current across the battery to purposefully break the passivation film (prevents loss of energy whilst in storage) but it doesn't always work break it 100%.  Either remove and reinsert battery 2-3 times until it does show 100% on screen, or use battery key to briefly short circuit battery before insertion by applying to both terminals for a split second.

* If you don't want your preferences to be easily changed then you can password protect the preferences menu by selecting in the preferences menu "password for settings" and type the password you choose. The next time you go into preferences menu it will ask for that password before going any further. If you later want to remove the password option then go into "password for settings" and delete the text.

* If you plan to use the android wear app to bolus or change settings then you need to ensure notifications from AndroidAPS are not blocked. Confirmation of action comes via notification.

* If you take your pump off for showering/bathing/swimming/sport etc then press and hold on the "Closed Loop" text on the main homepage and select "disconnect for..." however many minutes/hours you plan to disconnect for.  This will set your basal to zero for that time period.  If you connect your pump sooner than expected then press and hold "Suspended (X mins)" and select "Resume".  Your IOB will then be accurate for calculations on your return to the pump.

* For safety, recommendations made are based on not one CGM reading but the average delta.  Therefore if you miss some readings it may take a while after getting data back before AndroidAPS kicks in looping again.

* Within your Circadian Percentage Profile you have another chance to set your units to mg/dl or mmol/l separate to the preferences menu, don't forget to update this in both places! 

* There are several blogs with good tips to help you understand the practicalities of looping:
  * [Fine-tuning Settings](http://seemycgm.com/2017/10/29/fine-tuning-settings/) See my CGM
  * [Why DIA matters](http://seemycgm.com/2017/08/09/why-dia-matters/) See my CGM
  * [Limiting meal spikes](https://diyps.org/2016/07/11/picture-this-how-to-do-eating-soon-mode/) #DIYPS
  * [Hormones and autosens](http://seemycgm.com/2017/06/06/hormones-2/) See my CGM

Other tips and tricks can be found in the [Facebook group](https://www.facebook.com/groups/1900195340201874/)

Accessing logfiles
==================

* Connect phone to a computer in file transfer mode
* Locate log files in this directory or similiar (may little bit vary on different phones)


![AAPS log](../../images/aapslog.png)

* The current log is a .log file which can be viewed in a number of ways such as [LogCat](https://developer.android.com/studio/debug/am-logcat.html) in Android Studio, Log Viewer android app, or simply plain text. Previous log files are zipped and stored in folders in date/time order.  If sharing your log in [gitter](https://gitter.im/MilosKozak/AndroidAPS) when talking about a potential bug then unzip and upload the folder dated before the error occurred.

Dev branch
==========

The most stable version of AndroidAPS to use is that in the [Master branch](https://github.com/MilosKozak/AndroidAPS/tree/master).  It is advised to stay on the Master branch while you complete the Objectives and get practiced at looping.

However, the [Dev branch](https://github.com/MilosKozak/AndroidAPS/tree/dev) is a good place to see what features are being tested and to help iron out the bugs and give feedback on how the new features work in practice.  A short summary of some of the changes to old features or development of new features currently in the Dev branch is listed below, and links to any key issues known will be shared (if applicable).

**Build Variants**<br>
The number of build variants has been reduced to:
* full (i.e. recommendations automatically enacted in closed looping)
* openloop (i.e. recommendations given to user to manually enact)
* pumpcontrol (i.e. remote control for pump, no looping)
* nsclient (i.e. looping data of another user is displayed and careportal entries can be added)

Wear control can now be enabled or disabled direct from the phone settings; this gives parents more flexibility and control over the features their child can use.  The watch needs to be connected to the phone when toggling the settings - otherwise when it is connected again press re-sync from the watch or open the menu on the watch two times in a row.

**Profiles**<br>
Circadian Percentage Profile (both timeshift and percentage) can now work with any Profile.  You no longer need to select "Circadian Percentage Profile" in the config builder, simply change profile using profile switch and you will also have the option to to change timeshift and/or percentage too.  This means you can easily tell AndroidAPS to decrease your profile (basal, bolus and sensitivity) by 30% for 6 hours for example when exercising without having to copy and paste profiles.  Local Profile has also been redesigned.
Switching profiles can also now be triggered by NS Client (picking it up from a Nightscout Careportal entry) or by the Profile Switch in AndroidAPS.  It means you can use conditional statement based systems (e.g. IFTTT/Automate/Tracker) to automatically change your profile for you based on other inputs (e.g. calendar entries, physical location).

**DanaR/RS Bolus Speeds**<br>
In Preferences under DanaR/DanaRS pump settings you can select the default bolus speed used (12sec per 1u, 30sec per 1u or 60sec per 1u).

**Temp Targets Default**<br>
In Preferences under Other you can set default values for the different types of temp target (eating soon and activity).  When you select a temp target then if you choose for example "Eating Soon" from the drop down box, it will automatically populate the duration and value for you based on the figures you provided.

**GUI**<br>
The Overview layout has been improved, and more icons added.  DanaR communication is more detailed in status line.

**DanaRS driver**<br>
DanaRS driver has been added to work with new DanaRS pump available shortly from SOOIL.

**Rhino javascript engine**<br>
Transition to Rhino javascript engine.

As with all updates, previous code has been cleaned, improved and bugs fixed.

If you find a bug or think something wrong has happened when using the Dev branch, then view the [issues tab](https://github.com/MilosKozak/AndroidAPS/issues) to check whether anyone else has found it, or add it yourself if not.  The more information you can share here the better (don't forget you may need to share your [log files](https://github.com/MilosKozak/AndroidAPS/wiki/Accessing-logfiles)).  The new features can also be discussed in the [gitter room](https://gitter.im/MilosKozak/AndroidAPS).