[![Version](https://img.shields.io/badge/Symcon-PHPModul-red.svg)](#anleitung)
[![Version](https://img.shields.io/badge/Symcon-Version%20%3E=%205.2-green.svg)](#)
[![Code](https://img.shields.io/badge/Code-PHP-blue.svg)](#anleitung)

# Magic Home Wifi LED
Module für IP-Symcon ab **Version 5.2**  zur Steuerung des Magic Home Wifi RGB/w Controllers oder kompatible.

Da die neuen **dynamischen Formulare** benutzt werden ist eine vollständige **Konfiguration** nur über das **WebFront** möglich.

# Getestet mit
Magic Mini RGB/w Wifi Controller für LED Strip/Streifen. Funktioniert mit Alexa, Google Home, IFTTT, und Siri IR Fernbedienung Steuerung, 16 Mio Farben, 20 Dynamische Modi

![Magic Mini RGB/w Wifi Controller](img/tested1.png?raw=true "Magic Mini RGB/w Wifi Controller")

# Anleitung
Derzeit ist das Modul funktionsfähig jedoch ungeprüft bzw. nur mit RGBW Geräten, siehe oben, von mir getestet;-)

**Inhaltsverzeichnis**

1. [Steuerung](#1-steuerung)  
2. [Extras](#2-extras)
3. [Unterstützte Protokolle](#3-protokolle)
4. [Module](#4-module)
5. [Installation](#5-installation)
6. [Anmerkung](#6-anmerkung)

## 1. Steuerung
- An / Aus
- Farbe
- Helligkeit
- Weiß Kanal
- Extra Weiß Kanal
- Farbmodus 20 Dynamische Modi
- Farbmodus Geschwindigkeit

## 2. Extras
- Bearbeiten von Geräte Timern [1-6]
    - löschen von abgelaufenen Timern
    - erstellen oder ändern von Geräte timern
    - lesen und schreiben der Geräte Timerliste
    - die Timerliste wird permanent auf dem Gerät gespeichert und arbeitet unabhängig von IPS , vorausgesetzt die Gerätezeit ist aktuell.
- Geräte Uhrzeit lesen/setzen
    - Unterstützt automatisches aktuallieren der Gerätezeit nach stromausfall
- Arbeitet mit Rückkanal
    - Änderungen werden dadurch Zeitnah erkannt auch wenn das Gerät über die Andoid/Apple APP gesteuert wird
- Option zur Auswahl ob Daten dauerhaft auf dem Gerät gespeichert werden sollen
    - Daten wie Farbe, Weißkannal werden auf dem Gerät permanent gespeichert und bleiben auch nach einem Stromausfall erhalten.
- Manuelle Protokoll-Type Auswahl
- Manuelle RGB/w Protokoll Option
    - Abhängig vom Protokoll-Type (für LEDNET Original Aus, alle anderen Ein)
- Manuelle CheckSum Option
    - Einige Geräte benötigen eine Check Summe der übertragenen Daten

## 3. Protokolle
- MagicHome
- LEDNET
- LEDNET Original


## 4. Module
- Discover Modul zum finden der Geräte im Netzwerk
- Steuerung Modul zur Steuerung des Gerätes
- Sprachen EN, DE


## 5. Installation

**a. Controler im Netzwerk einrichten**

Ein neuer Controller muss **zuerst** auf dem Smartphone mit der zugehörigen APP **in** deinem **Netzwerk eingebunden** werden. Erst nach dem erstmaligen einrichten wird der Controller vom Discovery Modul erkannt.

```
TIPP
Da die mir bekannten Wifi Geräte nur das 2G Wifi unterstützen muss man beim erstmaligen einrichten
mit der Andoid/Apple APP auf folgendes achten:
Falls das 2G + 5G Wifi auf der gleichen SID funkt sollte das 5G während der Einrichtung auf dem Router
deaktiviert werden da es sonst Probleme beim erkennen bzw. einrichten des Wifi Gerätes geben kann.
Nach der Einrichtung kann das 5G wieder problemlos auf dem Router aktiviert werden.
```

**b. Installieren über Modules Instanz**

Die Webconsole von IP-Symcon mit _http://{IP-Symcon IP}:3777/console/_ öffnen. 

Anschließend den Objektbaum _Öffnen_.

![Objektbaum](img/objektbaum.png?raw=true "Objektbaum")	

Die Instanz 'Modules' unterhalb von Kerninstanzen im Objektbaum von IP-Symcon (>=Ver. 5.x) mit einem Doppelklick _Öffnen_

![Objektbaum](img/object_tree.png?raw=true "Objektbaum")	

und das Plus Zeichen drücken.

![Plus](img/plus.png?raw=true "Plus")
	
![ModulURL](img/add_module.png?raw=true "Add Module")

Im Feld die folgende Module URL eintragen und mit _OK_ bestätigen:

```
https://github.com/softbar/MagicHomeWifiLED 
```

Anschließend erscheint ein Eintrag für das Modul in der Liste der Instanz _Modules_    

Es wird im Standard der Zweig (Branch) _master_ geladen, dieser enthält aktuelle Änderungen und Anpassungen.
Nur der Zweig _master_ wird aktuell gehalten.

![Master](img/master.png?raw=true "master") 


**c. Einrichtung der Module**

In IP-Symcon nun zunächst mit einem rechten Mausklick auf **Discovery Instances** eine **neue Instanz** mit **Objekt hinzufügen** -> Instanz_ (_CTRL+1_ in der Legacy Konsole) hinzufügen, und **WifiBulb RGB/w Discover** auswählen.

![Add Discovery Instance](img/create_discover.png?raw=true "Add Discovery Instance")


  
![List](img/discover_list.png?raw=true "Gefundene Geräte")

Nun das gewünschte Gerät markieren und auf **Erstellen** oder **Alle Erstellen** klicken, die Instanz wird dann erzeugt.  

```
Die durch das Discovery Module erstellten Instanzen finden sich  im Objektbaum unter:
IP-Symcon -> Wlan RGB/w Geräte
```

## 6. Anmerkung


