---
title:  "node npm node-sass node-gyp fehler"
categories:
  - posts
tags:
  - npm
  - nodejs
---

Das Modul node-sass verwendet node-gyp. Dabei wird beim Installieren der Pakete (npm i) eine c++ Compilierung durchgeführt. 
Dazu müssen auf dem entsprechenden Windows Rechner ein paar Pakete installiert sein.

* Python 2
* Visual Studio 2017 Build Tools

Dazu wieder mal eine Admin Powershell öffnen und die Pakete installieren:

```

choco install -y python2 
npm install --global --production windows-build-tools

npm config set python "C:\Python27\python.exe" -global
npm config set msvs_version 2017 –global

```

Diese Build Tools tauchen zwar im Visual Studio Installer auf.. Nützt aber nichts. Sie sind ein recht einfacher Weg alles zu installieren.


Hier noch ein paar Links zum Thema:

* https://spin.atomicobject.com/2019/03/27/node-gyp-windows/
* https://danielwertheim.se/solution-to-issues-with-node-gyp-node-sass-on-windows/