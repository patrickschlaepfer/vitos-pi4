# vitos-pi4

VitOS läuft **nicht** auf einem Raspberry pi4 mit 8GB Memory. Auf einem pi4 mit 2GB läuft VitOS einwandfrei.

VitOS basiert auf Arch Linux.

Zur Steuerung wird die App (iOS/Android) VitOSManager benötigt.

## Links

* [Silent Angel VitOs](https://community.roonlabs.com/t/silent-angel-vitos/90551/19)
* [Installing Roon on Linux](https://help.roonlabs.com/portal/en/kb/articles/linux-install)

## Installation ROON Bridge

Der `INSTALL` Knopf in der der VitOSManager App scheint nicht zu funktionieren,
daher muss ROON-Bridge manuell installiert werden.

1. Login via `ssh` mit `root/root` auf den VitOS Pi
2. Erstellen des `which` Kommandos
```
[root@Raspberry-Pi-4B ~]# printf '#!/bin/bash\ncommand -v $@\n' > /usr/local/bin/which
[root@Raspberry-Pi-4B ~]# chmod +x /usr/local/bin/which
```
3. Updaten des Package Repos
```
pacman -Sy
```
4. Herunterladen der ROON Bridge Software
```
[root@Raspberry-Pi-4B ~]# curl http://download.roonlabs.com/builds/roonbridge-installer-linuxarmv7hf.sh --output roonbridge-installer-linuxarmv7hf.sh
[root@Raspberry-Pi-4B ~]# chmod +x roonbridge-installer-linuxarmv7hf.sh
[root@Raspberry-Pi-4B ~]# ./roonbridge-installer-linuxarmv7hf.sh
```

