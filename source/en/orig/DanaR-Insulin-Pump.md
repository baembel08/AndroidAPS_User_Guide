* In the pump go to Main Menu > Setting > User Option
* Turn on "8. Extended Bolus"

[[https://github.com/MilosKozak/AndroidAPS/wiki/images/danar1.png]]

* Go to Main Menu > Setting > Discovery
* In phone settings go to Bluetooth, scan for nearby devices, select your DanaR serial number and input your password (Default password is either 1234 or 0000).  If DanaR is not showing in scan then restart phone and take DanaR battery out, replace and start these two steps again.

* In AndroidAPS go to Config Builder and select the type of DanaR you have (DanaR, DanaR Korean, DanaRv2, DanaRS)
* Select Menu by tapping the 3 dots in the top right. Select Preferences.
* Select DanaR Bluetooth device, and click your DanaR serial number.
* Select Pump password, and input your password. (Default password is either 1234 or 0000)
* If you want AndroidAPS to allow basal rate above 200%, enable Use extended boluses for >200%. Note this means you cannot loop with high TBRs whilst using extended boluses for food.
* Set basal step on pump to 0.01 U/h