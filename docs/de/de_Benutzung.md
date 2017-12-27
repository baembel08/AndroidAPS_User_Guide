Benutzung
=========

Objectives - Richtlinien
========================

AndroidAPS hat eine Reihe an `Objectives`, die erfüllt werden müssen um dich durch die Funktionen und Einstellungen des Loopens zu führen. Sie garantieren, dass du alles korrekt eingestellt hast und verstehst was das System genau macht, somit du ihm vertrauen kannst.

Wenn du auf ein anderes Smartphone umsteigst, kannst du deine Einstellungen und den Fortschritt exportieren. Bei den drei Punkten, oben rechts, wähle _Export Settings_, es wird eine Benachrichtigung erscheinen wo die Preferences Datei gespeichert wird (normalerweise im Hauptordner des internen Speichers). Beim neuen Smartphone musst du diese Datei, dann in den gleichen Pfad kopieren, und anschließend _Import Settings_ wählen. Es werden alle mögliche Einstellungen, auch die Sicherheitseinstellungen, und der Fortschritt in den Objectives gespeichert. Falls du das nicht machst gehen alle deine Einstellungen (bei Benutzung des Local Profiles, auch das Profil), und Fortschritte nicht verfügbar sein. Deshalb solltest du immer wieder mal eine Sicherheitskopie machen, dass du im Falle eines Verlustes, Beschädigung, etc. deine Daten nicht verlierst.
 
* **Objective 1:** Visualisierung und Konstrolle einrichten, und die Basalrate und Faktoren überprüfen
  * Wähle die richtige BZ-Quelle. Siehe [BZ-Quelle](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Einstellungen.html#CGM - BZ Quelle) für Informationen.
  * Wähle deine Pumpe im ConfigBuilder (wähle Virtual Pump, wenn du eine Pumpe ohne Treiber für AAPS verwendest). Wenn du die Dana verwendest, versichere dich, dass du die [Dana R](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Einstellungen.html#danar-insulinpumpe) gelesen, und richtig eingestellt hast.
  * Folge den Einstellungen zu [Nightscout](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Einstellungen.html#nightscout) um sicher zu stellen, dass du deine Daten erhältst und anzeigen lassen kannst.
<br><br>_Es könnte sein, dass du für den nächsten BZ warten musst, damit ihn AAPS erhält und akzeptiert._
 
* **Objective 2:** Start mit Open Loop
  * Wähle Open Loop, entweder in den [Einstellungen](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Einstellungen.html#einstellungen), oder indem du den Loop Button drückst und hältst, dieser befindet sich links oben im Homescreen.
  * Aktiviere mindesten 20 vorgeschlagene temp. Basalraten manuell über einen Zeitraum von 7 Tagen (Falls du eine andere Pumpe verwendest, gebe die Vorschläge in der Pumpe ein und bestätige es in AAPS). Versichere dich, dass die Daten in AAPS und Nightscout angezeigt werden.
 
* **Objective 3:** Den Open Loop, mit seinen temp. Basal Empfehlungen, verstehen.
  *Versuche die Logik hinter den Empfehlungen zu verstehen indem du dir diese [determine basal logic](https://openaps.readthedocs.io/en/latest/docs/While%20You%20Wait%20For%20Gear/Understand-determine-basal.html), die Vorhersagelinie in AAPS/Nightscout und die Ergebnisse im OpenAPS Tab ansiehst.
<br><br>_Stoppe hier, wenn du den Open Loop mit der virtuellen Pumpe verwendest._

* **Objective 4:** Mit dem closed Loop mit Hypoabschaltung starten
  * Wähle Closed Loop von den Preferences, oder indem du den Open Loop Button links oben im Homescreen drückst und hältst.
  * Setze deinen Zielbereich, um sicher zu gehen, ein wenig höher als üblich.
  * Sehe dir an wie die temp. Basalraten aktiv sind, indem du die blaue Linie auf der Homescreen Grafik, oder in Zahlen darüber kontrollierst.
  * Gehe sicher, dass deine Einstellungen korrekt sind, wenn du über 5 Tage keinen Unterzucker mehr behandeln musstest, sollten die Einstellungen in Ordnung sein. Im anderen Falle solltest du deine Faktoren noch einmal kontrollieren.
<br><br>_Das System ist auf einen maxIOB von 0 begrenzt, d.h. dass der Loop eine Hypo abfangen kann, aber keine Steigungen, das System kann die BR nur erhöhen wenn der IOB unter 0 liegt und dadurch auf 0 bringen.._
 
* **Objective 5:** Feineinstellung des closed Loops, max IOB über 0 erhöhen und schrittweise den Zielbereich verringern
  * Erhöhe dein maxIOB über 0 über einen Zeitraum von einem Tag, standardmäßig wird eine Einstellung auf 2 vorgeschlagen, aber du solltest dich langsam rauf arbeiten bis du weißt welche Einstellung für dich in Ordnung ist.
  * Wenn du dir mit deiner Einstellung sicher bist, verringere deinen Zielwert schrittweise auf deinen gewünschten Wert.
<br><br>Das System erlaubt dir den Zielbereich im Bereich von 60-180 zu setzen._
 
* **Objective 6:** Basalrate und Faktoren nachjustieren, falls erforderlich, und Auto-Sens Aktivierung
  * Du kannst [Autotune](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autotune.html) um deine BR und Faktoren zu kontrollieren verwenden, oder einen altmodischen BR-Test machen.
  * Aktiviere [Auto-Sens](https://github.com/MilosKozak/AndroidAPS/wiki/Open-APS-features) über einen Zeitraum von 7 Tagen und kontrolliere die weiße Linie im Homescreen (Sen-Kästchen aktiviert), um zu sehen wie sich deine Sensitivität ändert, und kontrolliere regelmäßig im OpenAPS Tab wie AAPS deine BR und Faktoren ändert.
<br><br>_Vergiss nicht, dich in diese [Liste](http://bit.ly/nowlooping) einzutragen, wähle AAPS als deine DIY Software aus, falls du es noch nicht gemacht hast._
 
* **Objective 7:** Zusätzliche Funktionen für den alltäglichen Gebrauch aktivieren, wie Advanced Meal Assist (AMA)
  * Nun solltest du dich mit AAPS sicher fühlen und wissen, welche Einstellungen für deinen Diabetes am besten passen. Über einen Zeitraum von 14 Tagen kannst du zusätzliche Funktionen ausprobieren, welche dich noch mehr unterstützen.
  
OpenAPS-Funktionen
==================
  
  Manche Funktionen in AndroidAPS sind vom OpenAPS `oref0` Code, deswegen lies dir die OpenAPS Anleitung ebenso durch:
* [Advanced Meal Assist (AMA)](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#advanced-meal-assist-or-ama) nachdem du dir einen Bolus gegeben hast, kann das System schneller eine höhere temp. Basalrate wählen, vorausgesetzt du gibst die Kohlenhydrate verlässlich ein. Aktiviere die Option im Config Builder Reiter, jedoch musst du das siebte Ziel abgeschlossen haben, um AMA verwenden zu können.
* [Autosens](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#auto-sensitivity-mode) analysiert historische Daten und macht Anpassungen, wenn es bemerkt, dass die Sensitivität gestiegen/gesunken ist. Aktiviere es im Preferences Menü, dafür musst du das sechste Ziel abgeschlossen haben.
* [Temporary Targets/temporäre Ziele (Eating Soon and Activity Mode)](http://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/advanced-features.html#eating-soon-and-activity-mode-temporary-targets) temporäre Ziele (Temp Targets) sind ideal wenn du möchtest, dass der Loop auf einen anderen BZ Wert korrigiert, z.B. beim Sport (höheres Ziel), oder wenn du essen willst (niedrigeres Ziel -> BZ steigt nach dem Essen nicht so stark). Man kann die Temp Targets entweder über die Uhr, im Actions Reiter, oder indem man im Overview Reiter auf das aktuelle Ziel länger drückt. 
  Im Overview Reiter wird das Standard Ziel blau dargestellt, und das temporäre grün.
  
Circadian Percentage Profil
===========================
  
  * Um das Circadian Percentage Profil zu aktivieren, gehe in den Config Builder und wähle Enabled und Visible.
  * Gib im Circadian Percentage Profil Menü (CPP) dein Basis Profil ein. Dieses Profil kann auf zwei Arten modifiziert werden:
  * Timeshift - diese Option verschiebt alle Einstellungen um die eingestellte Zeit, z.B. im Falle, dass man Nachtschichten arbeitet, gibt man die Stundenanzahl an um die man früher/später schlafen geht/aufsteht.
  * Percentage - diese Option verändert alle Werte um die Prozent die man einstellt. Wenn du 130% einstellst, heißt das, dass du um 30% mehr Basal, mehr Bolus für Speisen und Korrektur bekommst. Dieses "geänderte" Profil wird an die Pumpe gesendet und wird als "normale" Basalrate abgegeben, der Loop arbeitet, dann mit diesen Daten. Zum Beispiel kann man diese Funktion in den verschiedenen Abschnitten des Hormonzyklus verwenden.
  
Profil Funktion ab Version 1.5
==============================

Seit der Version 1.5 hat sich die Funktion der Profile geändert.

Bis Version 1.46 waren die Profiländerungen sofort übernommen.

AAPS kann immer noch nach der alten Funktion funktionieren, bis du ein "Profile switch" mit einer Dauer von null (später erklärt) einstellst. Wenn man das macht, beginnt AAPS die Historie der Profile zu verfolgen, und jede neue Profiländerung benötigt ein neues "Profile switch" Event, auch wenn du das Profil in Nightscout änderst. Das geupdatete Profil wird sofort an AAPS gesendet, aber du musst ein "Profile switch" Event eingeben um die Änderungen verwenden zu können.
Internaly AAPS creates snapshot of profile with start date and duration and is using it within selected period. Duration of zero means infinite. Such profile is valid until new "Profile switch".

Falls du einen "Profile switch" mit einer Dauer einstellst, wird nach Ablauf auf das letzte Profil zurück gegriffen.

Falls du ein lokales Profil in AAPS verwendest (CPP, Simple, Local), musst du nur die Taste im Plugin drücken, diese stellt den "Profile switch" automatisch richtig ein.

Diese Funktion ermöglicht genauere Kalkulationen über die Vergangenheit, indem die gewechselten Profile berücksichtigt werden.

Im closed Loop Modus wird empfohlen "Sync Profile in Pump" zu aktivieren.


Profil Free Peak 0ref
=====================

Bei dem Profil "Free Peak 0ref" für Fiasp, kann eingegeben werden, wann die höchste Wirkdauer erreicht wird.

Der DIA wird dabei automatisch auf 5 Stunden gestellt, wenn er selbst nicht höher angegeben wurde im Profil.


Die folgende Erklärung ist leider auf Englisch, aber bei den Grafiken wird es noch mal deutlich.

http://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and-why-it-matters/

![DIA Erklärung von diabettech.com](https://i1.wp.com/www.diabettech.com/wp-content/uploads/2017/07/DIA-Clamp.jpg?w=892)
<small>(Quelle: diabettech.com)</small>

Bei vielen ist nach 3-4 Stunden praktisch keine merkbare Wirkung vom Fiasp mehr da, aber immer noch 0,0xx Einheiten vorhanden. Diese können dann z.B. bei Sport sich doch noch bemerkbar machen.

Daher verwendet AndroidAPS Minimum 5h als DIA.


SMS Befehle
===========

Gehe in deinen Einstellungen im  Android-Telefon zu Apps > AndroidAPS > Berechtigungen und aktiviere dort SMS.

In AndroidAPS gehe zu Preferences > SMS Communicator und trage die Telefonnummer(n) ein, die dazu berechtigt werden soll(en), Kommandos an AndroidAPS senden zu dürfen. ‚Allow remote commands via SMS' muss außerdem aktiviert warden.

Sende von einem der berechtigten Telefone eine SMS an das Android-Smartphone, auf de AndroidAPS installiert ist. Sende dazu einen der folgenden **fettgedruckten** Kommandos und das Smartphone wird mit einer Erfolgsmittelung oder dem angeforderten Status antworten. 

*BG*

- Letzter Blutzucker 125 vor 4min, Delta: -12mg/dl, IOB: 0.20E (Bolus: 0.10E Basal: 0.10E)

*LOOP STOP/DISABLE*

- Das „Loopen“ wurde deaktiviert

*LOOP START/ENABLE*

- Das „Loopen“ wurde aktiviert.

*LOOP STATUS*

- Das „Loopen“ ist deaktiviert
- Das „Loopen“ ist aktiviert
- Pausiert (10 min)

*LOOP SUSPEND 20*
- Das „Loopen“ wird für 20 Minuten unterbrochen.
 
*LOOP RESUME*
- Das „Loopen“ fortsetzen

*TREATMENTS REFRESH*
- Geräte aktualisieren 1 Empfänger

*NSCLIENT RESTART*
- NSCLIENT restarten 1 Empfänger

*DANAR*
- Letzte Verbindung: vor 1 Min. Temp: 0.00E/h @11:38 5/30min IOB: 0.5E Reserv: 34E Batt: 100

*BASAL STOP/CANCEL*
- Um die temporäre Basalrate zu stoppen, antworte mit dem Code EmF

*BASAL 0.3*
- Um eine Basalrate von 0.3E/h zu starten, antworte mit Code Swe
- Ferngesteuerte Basalraten-Einstellungen sind nicht erlaubt (wenn ferngesteuerte Kommandos nicht erlaubt sind)

*BOLUS 1.2*
- Um einen Bolus vo 1.2E abzugeben, antworte mit Code Rrt
- Ferngesteuerte Boli sind nicht erlaubt (wenn ferngesteuerte Kommandos nicht erlaubt sind)

*CAL 126*
- Um Kalibrierungswert von 126 zu senden, antworte mit Code Rrt
- Kalibrierung gesendet (wenn xSrip installiert ist. Kallibrierungen zu akzeptieren, muss in xDrip+ aktiviert sein)

Tipps und Tricks
================

* Die wichtigste Voraussetzung für den closed Loop ist, dass deine Basalrate und Faktoren genau sind. Die Einstellungen die der Loop für dich machen kann sind Sicherheitshalber begrenzt (siehe maximal erlaubte temporäre [Basalrate](https://openaps.org/reference-design/)), das heißt, dass du die vorhandenen Ressourcen nicht für eine schlecht eingestellte Basalrate verschwenden solltest. Falls der Loop z.B. vor dem Essen immer die Insulinzufuhr zurück dreht, heißt das höchstwahrscheinlich, dass du die Basalrate anpassen musst. Du kannst [autotune](https://openaps.readthedocs.io/en/latest/docs/walkthrough/phase-4/autotune.html) verwenden um deine Daten zu analysieren, und Vorschläge zur Änderung der Basalrate/Faktoren zu bekommen (Jedoch mit Vorsicht zu genießen, das System kann z.B. nicht unterscheiden, ob du wegen Sport zu niedrig wurdest, oder ob die Basalrate nicht passt), oder du kannst deine Basalrate mit einem "altmodischen" Basalratentest testen.

* Das Loopen kann die Batterie der Pumpe schneller aufbrauchen. Am besten sollte man die Batterie bei 25% wechseln, weil sich die Pumpe mit schwacher Batterie bei der Kommunikation schwer tut, und es nicht mehr lange dauert bis sie ganz leer ist. Du kannst in Nightscout eine Warnung einrichten, falls du mal vergessen solltest nach dem Stand zu sehen. Tricks um Energie zu sparen:
  * senke die Dauer der Bildschirmbeleuchtung (in der Dana einzustellen)
  * senke die Dauer der Bildschirmzeit (in der Dana einzustellen)
  * wähle als Benachrichtigung den Ton anstatt des Vibrierens (in der Dana einzustellen)
  * benutze die Tasten der Pumpe so selten wie möglich, optimal wäre wenn man sie nur benutzt beim auffüllen des Reservoirs, um vergangene Daten, Batteriestand und Reservoirmenge zu kontrollieren benutze AndroidAPS.

* Falls du nicht möchtest, dass man die Einstellungen einfach ändert, kannst du im Preferences Menü ein Passwort einstellen. Wenn du dann das nächste mal in das Preferences Menü gehst, wirst du zuerst aufgefordert das Passwort einzugeben, bevor du irgendwelche Einstellungen vornehmen kannst. Falls du die Option wieder deaktivieren möchtest, gehe zu "password for settings" und lösche die Zeichen.

* Wenn du die Android Wear App verwenden möchtest, achte darauf, dass AndroidAPS Benachrichtigungen auf der Uhr anzeigen darf.

* Wenn du die Pumpe mal abnimmst, drücke und halte im Hauptmenü den "Closed Loop" Text und wähle anschließend "disconnect for..." für die Zeit an Minuten die du vorhast, die Pumpe nicht an zu legen. Diese Option setzt eine temp. Basalrate von 0% für den eingestellten Zeitraum. Wenn du die Pumpe früher wieder anlegst, halte wieder die Taste am Bildschirm und wähle "Resume". Dein IOB wird dadurch genauer für die Berechnungen sein.

* Sicherheitshalber sind die Vorschläge nicht auf die einzelnen BZ Wert gerichtet, sondern anhand des durchschnittlichen Deltas, somit kann es sein, dass du im Falle, wenn du keine BZ Werte bekommen hast, es eine Weile dauern kann bis AndroidAPS wieder anfängt zu loopen.

* Im Circadian Percentage Profil hast du eine andere Chance deine Einheit zu mg/dl, oder mmol/l zu wechseln, abgesehen zum Preferences Menü, vergiss nicht zu updaten in beiden Fällen! 

* Es gibt verschieden Blogs (Englisch), wo es gute Tipps zum Loopen gibt:
  * [Warum die Wirkungsdauer von Insulin wichtig ist](http://seemycgm.com/2017/08/09/why-dia-matters/)
  * [Spitzen nach dem Essen verringern](https://diyps.org/2016/07/11/picture-this-how-to-do-eating-soon-mode/)
  * [Hormone und Autosens](http://seemycgm.com/2017/06/06/hormones-2/)

Andere Tipps und Tricks kann man in der [Facebook Gruppe](https://www.facebook.com/groups/1900195340201874/) finden.

Zugriff auf Logfiles
====================

* Verbinde das Smartphone mit dem Computer
* finde die Logfiles in diesem, oder ähnlichem Ordner (kann von Smartphone zu Smartphone verschieden sein)
    * Zur Erklärung: Dieser PC -> das Smartphone -> Interner Speicher -> Android -> data -> info.nightscout.androidaps -> files

![AAPS log](../../images/aapslog.png)

* Das aktuelle Logfile ist dasjenige, welches mit .log endet, dieses kannst du auf verschiedene Arten ansehen, z.B. mit [LogCat](https://developer.android.com/studio/debug/am-logcat.html) in Android Studio, Log Viewer Android App, oder einfach mit dem Text Editor. Ältere Logfiles sind gezippt und in Ordnern nach Datum und Zeit sortiert. 
  Wenn du die Logfiles in [gitter](https://gitter.im/MilosKozak/AndroidAPS) teilst, um über etwaige Bugs zu berichten, entzippe den Ordner mit der Zeit bevor und während dieser Bug aufgetreten ist, und lade ihn hoch.

Dev branch
==========

Verwenden Sie die stabilste Version von AndroidAPS, welche sich im [master](https://github.com/MilosKozak/AndroidAPS/tree/master) branch befindet. Es wird empfohlen, auf dem Master Branch zu bleiben, während Sie die Richtlinien komplettieren und Erfahrungen beim Looping sammeln.

Der [Dev](https://github.com/MilosKozak/AndroidAPS/tree/dev) Branch ist jedoch ein guter Ort zu sehen, welche Funktionen getestet werden und zu helfen, die Fehler auszubügeln. Und um Feedback aus der Praxis über die Funktionsweise der neuen Features zu geben. Eine kurze Zusammenfassung von einigen der Änderungen an alten Features oder Entwicklung neuer Features ist derzeit im <0 Dev 0> Branch unten aufgeführt. Hier gibt es auch Links zu wichtigen bekannten `Issues` (falls zutreffend), die geteilt werden.

**Varianten**<br>   
Die Anzahl der Build-Varianten wurde gesenkt auf:

* vollständig (d. h. Empfehlungen werden automatisch erlassen im `Closed Looping`)
* openloop (d. h. Empfehlungen für Benutzer, um sie manuell zu erlassen)
* PumpControl (d.h. Fernbedienung für Pumpe, kein Loop)
* nsclient (d. h. Loop Daten eines anderen Benutzers werden angezeigt und Careportal Einträge können hinzugefügt werden)

`Wear`Kontrolle kann jetzt aktiviert oder deaktiviert werden direkt aus den Smartphone Einstellungen; Dies gibt Eltern mehr Flexibilität und Kontrolle über die Funktionen, die ihr Kind verwenden kann. Die Smartwatch muss an das Smartphone angeschlossen werden, wenn die Einstellungen umgeschaltet werden - ansonsten, wenn sie wieder angeschlossen ist, drücken Sie Re-sync von der Smartwatch oder öffnen Sie das Menü auf der Uhr zwei Mal hintereinander.

**Profile**<br>   
Circadian Prozentsatz Profil (beides Timeshift und Prozentsatz) können nun mit jedem Profil arbeiten. Sie müssen nicht mehr "Circadian Prozentsatz Profil" im Config-Generator auswählen, das Profil mit Profilwahlschalter einfach ändern. Sie haben auch die Möglichkeit, Änderung Timeshift und/oder Prozentsatz zu ändern. Dies bedeutet, dass Sie leicht AndroidAPS konfigirieren können, Ihr Profil (basale, Bolus und Empfindlichkeit) um 30 % zu verringern für 6 Stunden zum Beispiel bei der Durchführung ohne Kopieren und Einfügen von Profilen. Lokales Profil wurde ebenfalls neu gestaltet. Wechseln der Profile kann nun auch durch den NS-Client (aus einem Nightscout Careportal Eintrag aufgenommen) oder durch die Profil-Schalter im AndroidAPS ausgelöst werden. Es bedeutet, das Sie auch mit bedingten Anweisungen basierten Systemen (z.B. IFTTT/automatisieren/Tracker) automatisch Ihr Profil ändern können, basierend auf anderen Eingängen (z. B. Kalendereinträge, Standort basiert).

**DanaR/RS Bolus Geschwindigkeiten**<br>   
In den Pumpeneinstellungen unter DanaR/DanaRS (12 Sek. pro 1u, 30 sec pro 1u oder 60 Sek. pro 1u) kannst du die Bolus Standardgeschwindigkeit einstellen.

**Standard-Temp-Ziele**<br>   
In den Einstellungen unter 'Other' können Sie Standardwerte für die verschiedenen Arten von temp Ziel (bald Ernährung und Bewegung) setzen. Wenn Sie ein temporäres Ziel auswählen, dann wenn Sie zum Beispiel "Bald Essen" aus dem Dropdown-Feld wählen, wird es automatisch die Dauer und den Wert für Sie veröffentlichen, basierend auf den Werten, die Sie zur Verfügung gestellt haben.

**GUI**<br>   
Das Übersicht-Layout wurde überarbeitet, und weitere Symbole hinzugefügt. Die DanaR Kommunikation ist in Statuszeile detaillierter sichtbar.

**DanaRS Treiber**<br>   
Der DanaRS Treiber wurde hinzugefügt, um mit der neuen DanaRS Pumpe zu kommunizieren, welche in Kürze von SOOIL zur Verfügung gestellt wird.

**Rhino-Javascript-engine**<br>   
Übergang zur Rhino-Javascript-Engine.

  
Wie mit allen Updates, wurde der vorherigen Code bereinigt, verbessert und von Fehlern behoben. <br />  
Wenn Sie einen Fehler finden oder denken, etwas Falsches bei der Verwendung des die <0>Dev<0>-Branch ist passiert dann schauen sie in die [Registerkarte Issues](https://github.com/MilosKozak/AndroidAPS/issues), um zu überprüfen, ob jemand diesen Fehler bereits gefunden hat, oder fügen Sie ihn selbt hinzu, falls nicht. Je mehr Informationen Sie hier teilen können, desto besser (nicht vergessen, müssen Sie Ihre [Log-Dateien](http://androidaps-user-guide.readthedocs.io/en/latest/de/de_Benutzung.html#zugriff-auf-logfiles) teilen). Die neuen Features können auch im [gitter chat room](https://gitter.im/MilosKozak/AndroidAPS) diskutiert werden.