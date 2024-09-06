# Raspi_onoff
Einfache möglichkeit einen Raspberry Pi ohne Datenverlust ein bzw. auszuschalten.
Es können Belibige GPIO's verwendet werden.

![Logo](./images/schematic.png)

Der pin "Run" ists der Testpad auf der rückseite des Zero 2W.

Die Led ist optional aber hilfreich den zustand Power off bzw. Power on zu erkennen.

Es weden nur zwei kleine Änderungen in der config.txt benötigt:

* Sperren des Run/Reset Pin während das Betriebssystem läuft
* shutdown zum abschaltennzubaktivieren
 
Die Initialisierung in der config.txt im bootverzeichnis:
```
gpio=27=op,dl 
dtoverlay=gpio-shutdown,gpio_pin=17,active_low="y"
```

Von der kommandozeile aus:
```shell
sudo sh -c 'echo "gpio=27=op,dl" >> /boot/firmware/config.txt'
sudo sh -c 'echo "dtoverlay=gpio-shutdown,gpio_pin=17,active_low=\"y\"" >> /boot/firmware/config.txt'
