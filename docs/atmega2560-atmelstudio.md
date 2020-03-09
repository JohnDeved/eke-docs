---
name: Atmelstudio Setup
menu: Atmega 2560
---

## Neues Projekt erstellen

Neue Projekte werden unter File -> New -> Project erstellt

![Neues Projekt erstellen](https://i.imgur.com/p9bflXv.png)

Folgender Dialog wird geöffnet:

![New project dialog](https://i.imgur.com/6KzC0er.png)

`Name:` - Name des Projektes

`Location:` - Lokaler Speicherpfad

`Solution name:` - Name der Solution (Solution = Container in dem mehrere Projekte gespeichert werden können)

Anschließend wird der verwendete Controller ausgewählt: (Atmega2560)

![Device selection](https://i.imgur.com/QOO60cB.png)

Bei Bestätigung des Dialogs wird das Projekt erstellt.

![Project creation](https://i.imgur.com/Lec9p4e.png)

![preview)](https://i.imgur.com/08Kfnnv.png)

## Target einrichten

Tools -> Device Programming

![add target](https://i.imgur.com/QQRfIN0.png)

Anschließend wird folgender Dialog geöffnet:

![add target](https://i.imgur.com/TDYUFp9.png)

`Select Tool:` Bei Verwendung des myAVR.de USB-ISP programmers `STK500` auswählen

`Select Serial Port:` Verwendeten COM Port angeben