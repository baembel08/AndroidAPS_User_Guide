CGM - BZ Quelle
===============

Für Dexcom Benutzer:
--------------------
_Mit xdrip…_<br>
* Falls noch nicht eingerichtet downloade [xdrip](https://github.com/NightscoutFoundation/xDrip) und folge den Anleitungen auf Nightscout ([G4 without share](http://www.nightscout.info/wiki/welcome/nightscout-with-xdrip-wireless-bridge), [G4 share](http://www.nightscout.info/wiki/welcome/nightscout-with-xdrip-and-dexcom-share-wireless), [G5](http://www.nightscout.info/wiki/welcome/nightscout-with-xdrip-and-dexcom-share-wireless/xdrip-with-g5-support)).
* In xdrip gehe zu Settings > Interapp Compatibility > Broadcast Data Locally und wähle ON.
* In xdrip gehe zu Settings > Interapp Compatibility > Accept Treatments und wähle OFF.
* Falls du mit AndroidAPS kalibrieren willst dann gehe in xdrip zu Settings > Interapp Compatibility > Accept Calibrations und wähle ON. Du solltest auch die Optionen in Settings > Less Common Settings > Advanced Calibration Settings kontrollieren.
* Wähle in AndroidAPS > CONFIG BUILDER > xdrip.

_Mit der Dexcom G5 App..._<Br>
* Zur Zeit nur im dev Branch, und in mmol/l (mg/dl version in Kürze verfügbar).
* Downloade die apk von [hier](https://github.com/dexcomapp/dexcomapp), es geht nur mit dieser.
* Deinstalliere die originale Dexcom App, falls du sie noch hast.
* Wähle im Config Builder Dexcom G5 App.

_Mit OTG cable ('traditional' Nightscout)…_<br>
* Falls noch nicht eingerichtet, dann downloade Nightscout Uploader app vom Play Store und folge den Einstellungen auf [Nightscout](http://www.nightscout.info/wiki/welcome/basic-requirements).
* Gib in den AndroidAPS Einstellungen > NSClient deine Nightscout URL und dein Nightscout API-Key ein.
* Wähle im CONFIG BUILDER > PROFIL > NS Profil (AndroidAPS).


Für FreeStyle Libre Nutzer:
---------------------------

_Mit xdrip..._<br>
* Falls noch nicht eingerichtet, dann downloade xdrip und folge der Anleitung auf:<br> 
• [LimiTTEer](https://github.com/JoernL/LimiTTer)  
• [Libre Alarm](https://github.com/pimpimmi/LibreAlarm/wiki) <br> 
• [BlueReader](https://unendlichkeit.net/wordpress/?p=680&lang=en)([Hardware](https://bluetoolz.de/wordpress/)).
* In xdrip gehe zu Einstellungen > Inter-App Einstellungen > Lokaler Broadcast und wähle AN.
* In xdrip gehe zu Einstellungen > Inter-App Einstellungen > Behandlungen annehmen und wähle AUS.
* Falls du mit AndroidAPS kalibrieren willst dann gehe in xdrip zu Einstellungen > Inter-App Einstellungen > Accept Calibrations und wähle AN. Du solltest auch die Optionen in Einstellungen > Erweiterte Einstellungen > Erweiterte Kalibrierung kontrollieren.
* Wähle in AndroidAPS > CONFIG BUILDER > xdrip.

_Mit Glimp..._<br>
* Falls noch nicht eingerichtet, dann downloade Glimp und folge der Anleitung auf [Nightscout](http://www.nightscout.info/wiki/welcome/nightscout-for-libre).
* Wähle in AndroidAPS > CONFIG BUILDER > Glimp.

Für Benutzer von MM640g oder MM630g:
====================================
* Falls noch nicht eingerichtet, dann downloade [600SeriesAndroidUploaer](http://pazaan.github.io/600SeriesAndroidUploader/) und folge der Anleitung auf [nightscout](http://www.nightscout.info/wiki/welcome/nightscout-and-medtronic-640g).
* Im 600 Series Uploader gehe zu Settings > Send to xdrip+ und wähle ON (Ankreuzen).
* Wähle MM640g im ConfigBuilder (in AndroidAPS).


Für Nutzer von anderen CGM Systemen mit Upload zu Nightscout:
=============================================================

Falls du ein anderes CGM System verwendest, das die Werte zu [Nightscout](http://www.nightscout.info) sendet, dann<br>
* Gib in AndroidAPS Preferences deine Nightscout Website und API secret ein.
* Wähle den NSClient im ConfigBuilder (in AndroidAPS).

Nightscout
==========

Es wird vorausgesetzt, dass du bereits eine eigene Nightscout Seite eingerichtet hast, falls nicht folge [Nightscout](http://www.nightscout.info/wiki/welcome/set-up-nightscout-using-heroku), um eine ausführliche Anleitung zur Einrichtung zu erhalten. Bei der unteren Anleitung findest du die Einstellungen die du zusätzlich noch ändern musst.
* Gehe zu https://portal.azure.com/ oder https://herokuapp.com/

* Wähle deinen App Namen.

* Drücke settings (azure), oder Settings > "Reveal Config Variables (heroku)

* Füge die Variablen hinzu oder ändere sie wie folgt:
  * `ENABLE` = `careportal boluscalc food bwp cage sage iage iob cob basal ar2 rawbg pushover bgi pump openaps`
  * `DEVICESTATUS_ADVANCED` = `true`
  * `PUMP_FIELDS` = `reservoir battery clock`
  * Various alarms can be set for [monitoring the pump](https://github.com/nightscout/cgm-remote-monitor#pump-pump-monitoring), battery % in particular is encouraged:
    * `PUMP_WARN_BATT_P` = `51`
    * `PUMP_URGENT_BATT_P` = `26`

[Nightscout](../images/nightscout1.png)

* Drücke Speichern.


DanaR-Insulinpumpe
==================


* Gehe zum Hauptmenü - Einstellen - Anwendermenü

* Aktiviere "8. Extended Bolus"

[Dana-R](../images/danar1.png])

* Gehe zum Hauptmenü -> Einstellen -> Suchen
* Gehe auf dem Handy zu den Bluetootheinstellungen und suche Geräte in der Nähe. Wähle die Seriennummer deiner Dana und gebe das Passwort ein (Standard ist entweder 1234, oder 0000). Falls die Dana nicht aufscheind, starte das Handy neu und wechsle die Batterie der Dana, wiederhole anschließend diesen Schritt.

* Gehe in AAPS zum Config Builder und wähle deine Dana Version (DanaR, DanaR Korean, DanaRv2, DanaRS).
* Klicke auf Preferences (3 Punkte rechts oben).
* Wähle DanaR Bluetooth device, und wähle deine Seriennummer aus.
* Wähle Pumpen Passwort, und gebe das Passwort ein (Standard ist entweder 1234, oder 0000).
* Falls du willst, dass AAPS Basalraten über 200% einstellen kann, musst du Benutze extended Bolus für hohe temp. Basal aktivieren. Falls du diese Option nicht aktivierst, kann AAPS die BR nicht auf über 200% erhöhen.
* Setze die Basalschritte in der Pumpe auf 0,01 U/h.


Einstellungen
=============

Passwort für Einstellungen
--------------------------

Dadurch können Sie ein Kennwort festlegen, um versehentliche oder nicht autorisierte Änderungen an Einstellungen zu vermeiden. Sie müssen hier ein Passwort eingeben, um auf die Einstellungen zugreifen zu können. Um die Passwort-Option innerhalb der Einstellungen zu löschen, ist der Text in diesem Feld zu entfernen.

Alter des Patienten
-------------------

Die Algorithmen sind für Patienten aufgrund des Alters verschieden. Das in Form von Kind, Teenager oder Erwachsener hier auswählen.

Allgemeines
-----------

* Wählen Sie Ihre Sprache hier. Wenn Ihre Sprache nicht verfügbar ist, oder nicht alle Wörter übersetzt werden, dann zögern Sie nicht, einige Vorschläge zu machen. Die Übersetzungsdateien finden Sie hier: [App > Src > Main > Res > Werte > Seiten](https://github.com/MilosKozak/AndroidAPS/blob/dev/app/src/main/res/values/strings.xml) oder Fragen Sie im [gesamten Chatraum](https://gitter.im/MilosKozak/AndroidAPS).
* Der Schnelleinstellungs Assistent ermöglicht es Ihnen, eine Schnelltaste für einen häufigen Snack oder eine Mahlzeit hinzufügen. Geben Sie Mahlzeitendetails auf dem Homescreen ein. Wenn Sie die Schaltfläche Schneller Assistent wählen, wird der Bolus für diese Kohlenhydrate berechnet anhand Ihrer aktuellen Werte (ohne Berücksichtigung von Blutzuckerwert oder Insulin an Bord).

Behandlungsportal
-----------------

"Eingegeben von" ist der in Ihrem Nightscout Careportal angezeigte Text "vom Feld eingegeben". Legen Sie etwas Sinnvolles für Namensgebung zurecht, egal ob es den App-Namen, den Namen von Personen oder den Smartphone-Namen betrifft. (z. B. Wenn Sie AndroidAPS mit dem NS-Client auf einem Smartphone verwenden das nicht das Smartphone des Patienten ist, ist es wichtig, die Smartphones zu unterscheiden).

Behandlungs-Sicherheit
----------------------

* Max Bolus [U] erlaubt ist dies die maximale Menge an Bolus-Insulin, die AAPS erlaubt ist, zu liefern. Diese Einstellung existiert als eine Sicherheitsgrenze, um einen massiven Boluswert durch versehentliche Eingaben oder Benutzerfehler zu verhindern. Es wird empfohlen, eine vernünftige Menge einzustellen, die in etwa der maximalen Menge an Bolus-Insulin entspricht, welche Sie jemals für eine Mahlzeit oder Korrektur Dosis benötigen werden. Diese Einschränkung gilt auch für die Ergebnisse der Bolus-Rechner.

Closed Loop
-----------

Sie können hier zwischen offenem und geschlossenen Loop umschalten. Offener Loop bedeutet TBR Vorschläge werden basierend Ihren Daten getroffen und als eine Benachrichtigung angezeigt, aber Sie müssen manuell akzeptieren und sie manuell in Ihre Pumpe eingeben. Geschlossener Loop bedeutet, dass TBR Vorschläge von Ihnen automatisch an Ihre Pumpe ohne Bestätigung oder Eingabe gesendet werden. Der Homescreen wird in der oberen linken Ecke angezeigt, ob Sie offen oder geschlossen Loopen. Das Drücken und Halten der Homescreen-Taste erlaubt Ihnen ausserdem, zwischen den beiden Loop Arten wechseln zu können.

Profil
------

Auswahl 'Sync Profil Pumpe' sendet Ihr aktuelles AndroidAPS Profil an die Pumpe als Basale Profil 1. Wenn AndroidAPS unterbricht oder die Verbindung zur Pumpe verloren geht, wird Ihre Pumpe auf das gleiche Profil als Standard zurückgesetzt, anstatt dass Sie es manuell in der Pumpe eingeben. Weitere Informationen zu Profilen finden Sie unter [Arbeiten mit Profilen in 1.5](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Benutzung.html#profil-funktion-ab-version-1-5).

Einstellungen der Pumpe
-----------------------

Die Optionen variieren hier je nachdem, welchen Pumpen Treiber Sie im "Config Generator" ausgewählt haben. Koppeln und einrichten Sie ihre Pumpe entsprechend den Anweisungen der [DanaR Insulinpumpe](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Einstellungen.html#danar-insulinpumpe) wo relevant.

NS-Client
---------

* Legen Sie Ihre Nightscout-URL hier: \[Heroku\](https://yourwebsitename.herokuapp.com) oder hier: \[Azure\](https://yourwebsitename.azurewebsites.net) und das "API Secret" (ein Kennwort mit 12 Zeichen in Ihrem Heroku oder Azure Variablen) an. Dadurch können Daten zwischen der Nightscout Website und AndroidAPS gelesen und geschrieben werden. Überprüfen Sie auf Tippfehler besonders hier, wenn die Website - einrichtung nicht weiter geht..
* 'Log app zu Nightscout starten' trägt eine Notiz in Ihrem Behandlungsportal-Einträgen jedes Mal ein , wenn die App gestartet ist. Die App sollte nicht mehr als einmal am Tag gestartet werden müssen, wenn es häufiger auftriit, lässt dieses ein Problem vermuten. 
* "Enable local broadcasts" leitet Ihre Careportal Daten an andere Apps auf dem Smartphone wie Xdrip weiter. 
* Mit "Alarm-Optionen" können Sie auswählen, welche Standard Nightscout Alarme über die App verwendet werden. Zum Einstellen der Alarm Werte ändern sie Ihre [Heroku oder Azure Variablen](http://www.nightscout.info/wiki/welcome/website-features#customalarms).

SMS-Communicator
----------------

Diese Einstellung ermöglicht die Fernsteuerung der App durch SMS-Anweisungen zum Patienten-Smartphone, das der App folgt, wie die Aussetzung des Loops oder Bolusing. Weitere Informationen sind in [SMS-Befehle](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Benutzung.html#sms-befehle) beschrieben.

Andere
------

* Sie können Standardwerte für Ihre temporären Ziele hier eingeben, weitere Informationen finden Sie unter [Open APS-Funktionen](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Benutzung.html#openaps-funktionen). 
* Sie können Standard Prime Mengen eingeben - dieses wird die Pumpe auf den angegebenen Wert vorbereiten. Das Insulin wird wie abgegebens Insulin aus dem Reservoir bewertet aber nicht in IOB Berechnungen berücksichtigt. Schlagen Sie in der Anleitung für Ihre Kanüle-Box nach, für wieviele Einheiten je nach Länge der Nadel und Schlauchlänge vorbelegt werden sollten.
* Sie können die Anzeige für den Homescreen ändern und sehen, ob die Werte in den Zielbereichen liegen. Beachten Sie, dass dieses nur das Aussehen des Graphen ändert, nicht aber die Zielbereiche oder Berechnungen.
* "Tab-Reiter Verkürzen " erlaubt Ihnen, weitere Tab-Reiter auf dem Bildschirm zu sehen, zum Beispiel wird die "Open APS" Registerkarte zu 'OAPS', 'Objectives' wird zu 'Obj', etc.

Erweiterte Einstellungen  erfordert mehr Arbeit
------------------------------------------------

* OpenAPS MA 
  * Verwenden Sie immer kurze durchschnittliche Deltas statt... Die Aktivierung dieser Einstellung ist nützlich, wenn Daten aus ungefilterten Quellen wie xDrip +, im Gegensatz zu gefilterten Quellen wie einem offiziellen Dexcom-Empfänger verwendet werden. Gefilterte Daten erscheint glatt, während ungefilterte Daten gestreut erscheinen können. Ungefilterte Daten könnte dazu führen, dass AndroidAPS temporäre Basal Raten Änderungen mehr als erforderlich sind, vornimmt im Vergleich zur Reaktion von OpenAPS Algorithmen auf die gestreuten Daten. Mit Aktivierung dieser Einstellung wird der OpenAPS-Algorithmus das kurze durchschnittliche Delta (die durchschnittliche Veränderung des Blutzuckers in den letzten 15 Minuten) anstelle der letzten Blutzuckerwerte verwenden. Dieses wirkt sich effektiv als "Glättung" der Daten aus und versucht, alle gestreuten Werte zu kompensieren.

Benutzer von Abbot Freestyle Libre Sensoren, die ihre Datenerfassung von Glukose über Geräte wie LimiTTer machen, werden vielleicht bessere Ergebnisse mit AAPS erhalten.


AAPS funktioniert am besten, wenn die Blutzuckerdaten glatt und konsistent sind. Wenn Sie xDrip + als Datenquelle verwenden, können Sie einige Maßnahmen ergreifen, um das Rauschen in den Daten zu reduzieren.

Benutzer von Abbot Freestyle Libre-Sensoren, die ihre Blutzuckerdaten über Geräte wie LimiTTers sammeln, können feststellen, dass diese Einstellungen zu besseren Ergebnissen mit AAPS führen.

**Smooth Sensor Noise** In xDrip + Einstellungen> xDrip + Display-Einstellungen stellen Sie sicher, dass das Smooth Sensor Noise eingeschaltet ist. Dieses versucht eine Glättung auf verrauschte Daten anzuwenden.

** Glattes Sensorrauschen (ultrasensitiv). ** Wenn Sie in xDrip + immer noch verrauschte Daten sehen, können Sie aggressiveres Glätten mit der Einstellung Glattes Sensorrauschen (ultrasensitiv) anwenden. Dies wird versuchen, eine Glättung sogar bei sehr niedrigen Pegeln von detektiertem Rauschen anzuwenden. 

Der Engineering Mode in xDrip+ aktiviert erweiterte und experimenntelle Funktionen innerhalb der App.

Um den Engineering Mode zu Aktivieren, Gehen sie auf dem xDrip+ Hauptmenü und Klicken Sie auf das Behandlungs - Icon an der rechten oberen Seite (symbolisiert durch eine Spritze). Danach Drücken und Halten sie das Microphon Icon am rechten unteren Ende des Treatment Displays. Im Textfeld, das sich öffnet, geben Sie "enable engineering mode" ein und Klicken sie auf *Done*. Der Engineering Modus ist jetzt aktiviert.

Navigieren Sie dann zu Einstellungen> xDrip + Display-Einstellungen und aktivieren Sie Sensorrauschen glätten (ultrasensitiv).



Watchfaces
==========

In AndroidAPS ist es möglich, dass man die Pumpe über Android Wear Uhren kontrolliert. Um diese Möglichkeit zu nutzen, musst du beim [Kompilieren der App](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Installation.html#apk-erstellen) die Build Variante "fullWearcontrolRelease" wählen.
In AndroidAPS, im Config Builder, musst du dann noch `enable Wear` aktivieren. Es gibt verschiedene Watchfaces zum auswählen, enthalten sind durchschnittliches Delta, IOB, zur Zeit aktive Temp.Basalrate, das Basalprofil, und deine BZ Werte. Du kannst die AndroidAPS Watch App, auch verwenden, um ein Temp Target zu setzen, Bolus ab zu geben, den Bolus Wizard verwenden, Infusionset füllen, und den Status vom Loop und der Pumpe kontrollieren. 
Stelle sicher, dass AndroidAPS die Erlaubnis hat, um Benachrichtigungen auf der Uhr anzuzeigen (sonst kann man die Eingaben nicht bestätigen). Die Eingaben werden bestätigt in dem man die Benachrichtigung auf der Uhr öffnet, einmal wischt und bestätigt.

In Android Wear 2.0 installiert sich das Watchface nicht von alleine. Du musst in den Playstore der Uhr gehen, und unter der Kategorie "installierte Apps auf dem Smartphone" AAPS aktivieren. Aktiviere ebenalls Auto Update.

Falls du ein anderes System zum Loopen verwendest und deine Daten, oder die deines Kindes/Verwandten, auf der Uhr sehen möchtest, kannst du auch einfach nur die Watch APK kompilieren. 
Um nur die Watch APK zu kompilieren folge der [Anleitung](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Installation.html#apk-erstellen) und wähle die Build Variante "nsclientWearRelease".

Pebble Nutzer können das [Urchin watchface](https://github.com/mddub/urchin-cgm) benutzen um ihre Loop Daten (vorausgesetzt sie sind auf Nightscout) zu sehen, aber mit dieser Methode ist es nicht möglich die Pumpe und AndroidAPS zu steuern.
Du kannst Felder wählen um, z.B. IOB, aktiver temp. Basalrate und Vorhersage, anzeigen zu lassen. Falls du open loopst kannst du [IFTTT](https://ifttt.com/) benutzen um ein kleines Programm erstellen, welches bestimmt, wenn eine Benachrichtigungen von AndroidAPS kommt, eine SMS oder Benachrichtigung anzeigt.