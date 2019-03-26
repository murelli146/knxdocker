# Beschreibung knxdocker

knxd als Dockerimage speziell für Portainer zum einfachen installieren am Timberwolfserver.

Zugriff auf den knxd über das bidge Netzwerk zur kommunikation unter den Containern.

Hardware: In dieser Konfiguration wurde eine tpuart in den Container gelinkt (über /etc/knxd/knxd.ini können belibige Schnittstellen eingestellt werden)

Verfügbar auf [GitHub](https://github.com/murelli146/knxdocker) und [Docker Hub](https://hub.docker.com/r/murelli146/knxdocker)

Wer mich etwas Unterstützen möchte:

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/murelli146?locale.x=de_DE)


# Installation über Portainer

## Volume erstellen:
Name: knxd-conf > "Create the Volume" drücken.

## Container erstellen:
```
Name: knxdocker
Image: murelli146/knxdocker
> "Deploy the Container"
```
## Container einstellen
```
Volumes mapping > container: /etc/knxd -> volume: knxd-conf
Restart policy > value: always
Runtime & Resources > host: /var/husky/devices/ftdi_usb_serial_converter_ftDHEM5D   container: /dev/ttyS0
> "Deploy the Container"
```

# Konfiguration

Alle relevanten Dateien sind im /etc/knxd Ordner.

Um auf die Dateien zu zugreifen, verwendet man am besten den [SSH Container](https://forum.timberwolf.io/app.php/kb/viewarticle?a=70 )

knxd konfiguration bitte [hier](https://github.com/knxd/knxd/blob/master/doc/inifile.rst) , [hier](https://github.com/knxd/knxd/wiki) und [hier](https://knx-user-forum.de/forum/projektforen/knxd/1338248-konfiguration-plausibel) nachlesen
