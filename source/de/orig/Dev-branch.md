Verwenden Sie die stabilste Version von AndroidAPS, welche sich im [master](https://github.com/MilosKozak/AndroidAPS/tree/master) branch befindet. Es wird empfohlen, auf dem Master Branch zu bleiben, während Sie die Richtlinien komplettieren und Erfahrungen beim Looping sammeln.

Der [Dev](https://github.com/MilosKozak/AndroidAPS/tree/dev) Branch ist jedoch ein guter Ort zu sehen, welche Funktionen getestet werden und zu helfen, die Fehler auszubügeln. Und um Feedback aus der Praxis über die Funktionsweise der neuen Features zu geben. Eine kurze Zusammenfassung von einigen der Änderungen an alten Features oder Entwicklung neuer Features ist derzeit im <0 Dev 0> Branch unten aufgeführt. Hier gibt es auch Links zu wichtigen bekannten `Issues` (falls zutreffend), die geteilt werden.

**Varianten**   
Die Anzahl der Build-Varianten wurde gesenkt auf:

* vollständig (d. h. Empfehlungen werden automatisch erlassen im `Closed Looping`)
* openloop (d. h. Empfehlungen für Benutzer, um sie manuell zu erlassen)
* PumpControl (d.h. Fernbedienung für Pumpe, kein Loop)
* nsclient (d. h. Loop Daten eines anderen Benutzers werden angezeigt und Careportal Einträge können hinzugefügt werden)

`Wear`Kontrolle kann jetzt aktiviert oder deaktiviert werden direkt aus den Smartphone Einstellungen; Dies gibt Eltern mehr Flexibilität und Kontrolle über die Funktionen, die ihr Kind verwenden kann. Die Smartwatch muss an das Smartphone angeschlossen werden, wenn die Einstellungen umgeschaltet werden - ansonsten, wenn sie wieder angeschlossen ist, drücken Sie Re-sync von der Smartwatch oder öffnen Sie das Menü auf der Uhr zwei Mal hintereinander.

**Profile**   
Circadian Prozentsatz Profil (beides Timeshift und Prozentsatz) können nun mit jedem Profil arbeiten. Sie müssen nicht mehr "Circadian Prozentsatz Profil" im Config-Generator auswählen, das Profil mit Profilwahlschalter einfach ändern. Sie haben auch die Möglichkeit, Änderung Timeshift und/oder Prozentsatz zu ändern. Dies bedeutet, dass Sie leicht AndroidAPS konfigirieren können, Ihr Profil (basale, Bolus und Empfindlichkeit) um 30 % zu verringern für 6 Stunden zum Beispiel bei der Durchführung ohne Kopieren und Einfügen von Profilen. Lokales Profil wurde ebenfalls neu gestaltet. Wechseln der Profile kann nun auch durch den NS-Client (aus einem Nightscout Careportal Eintrag aufgenommen) oder durch die Profil-Schalter im AndroidAPS ausgelöst werden. Es bedeutet, das Sie auch mit bedingten Anweisungen basierten Systemen (z.B. IFTTT/automatisieren/Tracker) automatisch Ihr Profil ändern können, basierend auf anderen Eingängen (z. B. Kalendereinträge, Standort basiert).

**DanaR/RS Bolus Geschwindigkeiten**   
In den Pumpeneinstellungen unter DanaR/DanaRS (12 Sek. pro 1u, 30 sec pro 1u oder 60 Sek. pro 1u) kannst du die Bolus Standardgeschwindigkeit einstellen.

**Standard-Temp-Ziele**   
In den Einstellungen unter 'Other' können Sie Standardwerte für die verschiedenen Arten von temp Ziel (bald Ernährung und Bewegung) setzen. Wenn Sie ein temporäres Ziel auswählen, dann wenn Sie zum Beispiel "Bald Essen" aus dem Dropdown-Feld wählen, wird es automatisch die Dauer und den Wert für Sie veröffentlichen, basierend auf den Werten, die Sie zur Verfügung gestellt haben.

**GUI**   
Das Übersicht-Layout wurde überarbeitet, und weitere Symbole hinzugefügt. Die DanaR Kommunikation ist in Statuszeile detaillierter sichtbar.

**DanaRS Treiber**   
Der DanaRS Treiber wurde hinzugefügt, um mit der neuen DanaRS Pumpe zu kommunizieren, welche in Kürze von SOOIL zur Verfügung gestellt wird.

**Rhino-Javascript-engine**   
Übergang zur Rhino-Javascript-Engine.

<br />  
  
Wie mit allen Updates, wurde der vorherigen Code bereinigt, verbessert und von Fehlern behoben. <br />  
Wenn Sie einen Fehler finden oder denken, etwas Falsches bei der Verwendung des die <0>Dev<0>-Branch ist passiert dann schauen sie in die [Registerkarte Issues](https://github.com/MilosKozak/AndroidAPS/issues), um zu überprüfen, ob jemand diesen Fehler bereits gefunden hat, oder fügen Sie ihn selbt hinzu, falls nicht. Je mehr Informationen Sie hier teilen können, desto besser (nicht vergessen, müssen Sie Ihre [Log-Dateien](https://github.com/MilosKozak/AndroidAPS/wiki/Accessing-logfiles) teilen). Die neuen Features können auch im [gitter chat room](https://gitter.im/MilosKozak/AndroidAPS) diskutiert werden.