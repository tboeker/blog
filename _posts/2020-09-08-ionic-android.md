---
title:  "Ionic Cordova Android Build"
categories:
  - posts
tags:
  - npm
  - nodejs
  - ionic
  - cordova
---

Ich musste für eine Fehlersuche eine Ionic App für Android im Debug Modus erstellen. Nur leider war auf meinem Windows PC kein Android Sdk oder Android Studio installiert. Nun hatte ich aber keine Lust das große Studio zu installieren. 

Hier sind die Schritte, was alles installiert werden muss wenn man einfach nur mal ne Android App builden möchte.


Zuerst mittels Chocolatey die Pakete Android SDK und Gradle installieren:

```
choco install -y android-sdk
choco install -y gradle
```

Dann die Android Build Tools im SDK installieren:

```
cd C:\Android\android-sdk\tools\bin
.\sdkmanager.bat "build-tools;19.1.0"
```

Jetzt den Ionic Build durchführen werden:

```
npx ionic cordova build android
```

Am Ende wird der Pfad zum apk ausgegeben.

Dieses apk File jetzt mit adb auf dem Gerät installiert werden:

```
adb install c:\...\xxx.apx
```

Hinweis: Im neuen Windows Terminal mit Powershell wurden die Pfade nicht gefunden. Es scheint da ein Problem mit den Umgebungsvariablen zu geben. Daher habe ich das ganze im guten alten Command Prompt ausgeführt.



