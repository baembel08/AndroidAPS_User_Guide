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

* Es gibt verschieden Blogs (Englisch), wo es gute Tipps zum loopen gibt:
  * [Warum die Wirkungsdauer von Insulin wichtig ist](http://seemycgm.com/2017/08/09/why-dia-matters/)
  * [Spitzen nach dem essen verringern](https://diyps.org/2016/07/11/picture-this-how-to-do-eating-soon-mode/)
  * [Hormone und Autosens](http://seemycgm.com/2017/06/06/hormones-2/)

Andere Tipps und Tricks kann man in der [Facebook Gruppe](https://www.facebook.com/groups/1900195340201874/) finden.
