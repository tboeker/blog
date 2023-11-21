---
title:  "Android Emulator flackert"
categories:
  - posts
tags:
  - npm
  - nodejs
  - ionic
  - capacitor
---

Hin und wieder kommt es vor, dass der In-App Browser einer Android App im Emulator unter Windows flackert. Das passiert zum Beispiel beim öffnen der "Microsoft Login" Seite.

Gehe in den Order `%USERPROFILE$\.android\avd`.

Hier gibt es dann für jeden angelegten Emulator ein weiteres Verzeichnis.

Öffne in dem entsprechenden Verzeichnis die Datei: `config.ini`

Die folgenden Einstellungen müssen gesetzt sein:

`
hw.gpu.enabled=yes
hw.gpu.mode=software
`