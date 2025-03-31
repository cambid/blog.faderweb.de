---
title: "Backupday - und mein Setup"
date: 2025-03-31T17:07:37+02:00
draft: false
tags:
- tools
---

Wie passend heute ist ja World Backupday und ich hab im März mein Backup umgestellt.

Ich bin ja von Commvault begeistert, aber das ist für ein privates Backup doch
etwas übertrieben.

Bisher hatte ich dulicity im Einsatz, aber da war ich in letzter Zeit nicht
mehr wirklich zufrieden. Da auch das bisherige Backupziel nicht mehr existiert
und ich damit eh eine neue Lösung aufsetzen musste, konnte ich auch gerade

Voraussetzungen:

- automatisch mit Zeitplänen, aber auch manuell
- Benachrichtigungen mindestens per E-Mails
- Logfiles
- differentielles Backup
- verschiedene Speicherorte
- verschlüsselt
- flexibel konfigurierbar
- lesbare Konfiguration

Ziele:

- Hetzner Storage Box via SFTP
- lokales Synology per SMB
- manuelle Backups auf eine USB-C-SSD

Tools:

- restic
- resticprofile

Technisch kann restic alles was ich brauche und noch viel mehr. Mit
resticprofile lässt sich die Konfiguration auch schön in YAML/TOML schreiben.
JSON oder HCL geht auch, aber das brauche ich nicht. Das Scheduling per
systemd-timer kann es auch direkt erledigen.

Das Setup war schnell erledigt:

- YAML schreiben
- Job anwerfen
- Profit

Das initiale Backup hat ein paar Stunden gehabt und den Laptop gut ausgelastet,
aber seitdem sind es nur noch wenige Minuten.

Meine Konfigurationen findet sich im [Dotfile-Repo auf
Github](https://github.com/cambid/dotfiles/tree/main/resticprofile)

Und das Zusatzfeature mit restic/resticprofile lassen sich die Snapshots
readonly mounten und live browsen.

Ich bin gerade mit dem neuen Backup zufrieden und Spass hat es auch gemacht.
