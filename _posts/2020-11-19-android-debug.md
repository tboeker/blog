---
title:  "Android Cordova Chrome Debugging"
categories:
  - posts
tags:
  - npm
  - nodejs
  - ionic
  - cordova
---

Heute wollte ich eine Cordova Android App Debuggen. Wenn das APK im Debug MOdus erstellt wurde, kann dies mit den Chrome Tools passieren.

Zuerst das APK installieren. Vielleicht muss vorher die Installation aus unsicheren Quellen erlaubt werden.

Dann den Entwicklermodus aktivieren. Dazu öffnet man die Einstellungen / Geräteinformationen. Dann ganz oft hintereinander auf die Zeile Buildnummer tippen. Irgendwann erscheint eine Meldung, dass der Entwicklermodus aktiv ist.

Dann den Einstellungen / Entwickleroptionen öffnen. USB-Debugging aktivieren.

Gerät per USB an den PC anschließen.

Anschließend im Chrome die devices öffnen: ```chrome://inspect/#devices```

Hier sollte jetzt das Gerät aufgelistet werden...

Bei mir ist das nicht der Fall, also erstmal prüfen, ob das Gerät mit adb gefunden wird.
Also eine Command Line öffnen und ```adb``` eingeben.

Auf meimem System ist adb nicht installiert. Also das erstmal erledigen mit ```choco install adb```

Jetzt mit  ```adb devices``` prüfen ob das Gerät bereit ist. Bei mir wird das Gerät zwar aufgelistet, allerdings steht es im Status "unauthorized".

Also nochmal in die Android "Einstellungen / Entwickleroptionen / USB_Debug Berechtigungen löschen". Dann das USB Kabel abziehen und neu einstecken und die Frage nach dem Trusted Device bestätigen.

Jetzt mit  ```adb devices``` prüfen ob das Gerät bereit ist. Das Gerät wird jetzt aufgelistet im Status "device".

Jetzt noch einmal im Chrome die devices öffnen: ```chrome://inspect/#devices```

Und siehe da, das Gerät wird aufgelistet.