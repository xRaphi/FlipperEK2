# Inhaltsverzeichnis
[Erste Schritte](#erste-schritte)
- [Allgemeine Informationen](#allgemeine-informationen)
- [Infrarot](#infrarot)
- [NFC](#nfc)
- [qFlipper installieren + Funktionen](#qflipper-installieren--funktionen)

[Bad_USB](#bad-usb-projekt)
- [Vorbereitungen](#vorbereitungen)
- [Commands](#commands)
- [Testen](#testen)

# Erste Schritte

## Infrarot
Es gibt 3 Hauptfunktionen beim Infrarot:

1. **Universal Remotes**: Damit kann man Geräte wie TVs, Projektoren, Audio Player und Klimaanlagen steuern. Man kann diese ein- und ausschalten sowie die Lautstärke ändern. Die verfügbaren Signale sind jedoch begrenzt.

2. **Learn New Remote**: Mit dieser Funktion kann man neue Signale speichern. Dazu muss man mit einer Fernbedienung den Knopf drücken, der gespeichert werden soll. Der Flipper nimmt das Signal auf und kann es später simulieren und speichern.

3. **Saved Remotes**: Hier kann man auf die gespeicherten Infrarot-Signale zugreifen und sie erneut verwenden.

## NFC
Mit der NFC-Funktion kann man Karten einscannen, simulieren und speichern. Es gibt 3 Hauptfunktionen:

1. **Read**: Diese Funktion liest die Karte aus, um einige Details zu erhalten, wobei viele Informationen geschützt sind.

2. **Detect Reader**: Der Flipper erkennt NFC-Lesegeräte. Der Vorgang ist derselbe wie bei "Read".

3. **Saved**: Hier kann man alle gespeicherten Karten simulieren, bearbeiten, umbenennen oder löschen.

## qFlipper installieren + Funktionen
qFlipper ist ein Programm für den PC, das die Nutzung des Flippers erleichtert. Man kann Updates installieren und den Flipper digital steuern. 

1. Lade qFlipper [hier](https://flipperzero.one/update) herunter.
2. Verbinde den Flipper und installiere das Update.
3. Man kann den Flipper vom PC aus steuern, was praktisch für Screenshots ist.

# Bad-USB Projekt

Mein Hauptprojekt den Flipper kennenzulernen und zu verstehen wie man Scripte Programmiert.


## Commands
Einige grundlegende Commands sind:

- **REM**: Kommentar
- **STRING**: Gibt alles ein, was hinter STRING steht (z.B. STRING abc123!.?)
- **GUI**: Windows-Taste (in Kombination z.B. GUI r)
- **DELAY**: Verzögerung in Millisekunden
- **ENTER**: Enter-Taste (gleich wie CTRL, ALT, SHIFT)

## Probleme
Es gab ein Problem beim Stummschalten des Tons in der Powershell, da kein entsprechender Command verfügbar war. Ich fand eine Lösung mit [NirCmd](https://www.nirsoft.net/utils/nircmd.html) von NirSoft. 

1. Lade NirCmd herunter und führe es als Administrator aus.
2. Klicke auf "Copy to Windows Directory".

## Testen
Um ein Script auf dem Flipper auszuführen:

1. Speichere das Script als .txt-Datei auf dem Laptop.
2. Öffne qFlipper und gehe zum File Tab.
3. Finde den Ordner bad-usb und ziehe die Datei per drag and drop hinein.
4. Wähle auf dem Flipper Bad USB, dann das Script und führe es aus.

```python
REM Titel: Syt_EK
REM Author Raphael Troppmann
REM Version 1.2
REM Öffnet Chrome (Browser) und Rickrollt dich. Nach 7,5 Sekunden
REM angaben in Millisekunden

REM Öffnet windows Notepad
DELAY 500
GUI r
DELAY 500

REM Chrome öffnen und Video abspielen
GUI r
DELAY 500
STRING chrome.exe https://www.youtube.com/watch?v=dQw4w9WgXcQ
ENTER
DELAY 1000
REM Vollbild
F11

REM Windows + L (Sperrt den Bildschirm)
DELAY 7500
GUI l

ENTER
