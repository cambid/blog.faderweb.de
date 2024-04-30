---
title: "JSON-Tools für die Shell"
date: 2022-10-30T20:37:26+02:00
draft: false
tags:
 - tooltip
---

Das Format JSON setzt sich ja immer mehr durch und ich find es super.

Allerdings bin ich fast nur auf der Shell unterwegs und da sind die teilweise
eher sperrig. Aber es gibt Abhilfe dafür. Hier einige von mir eingesetzte
Tools. Die sind sicher nicht vollständig. Falls ihr weitere Tools im
JSON-Kontext empfehlen könnt, dann bin ich um Kommentare froh.

## Anzeige

Zur Anzeige von JSON reicht eigentlich cat oder bat, aber bei langen
JSON-Dateien auf einer Zeile wird das dann schnell unübersichtlich und
Syntax-Highlighting für unterschiedliche Typen hat man dann auch nicht.

[fx](https://github.com/antonmedv/fx) oder [jless](https://jless.io/) bieten
hier Abhilfe. Diese können sowohl auf Dateien als auch in Pipes verwendet
werden.

## Erstellung von JSON-Objekten

Manchmal braucht es nicht nur die Anzeige oder die Bearbeitung, sondern man
will ganz neue JSON erstellen. Das geht super mit
[jo](https://github.com/jpmens/jo)

Folgendes Beispiel mit Ein- und Ausgabe:

```bash
jo -p name=jf id=13 parser=false detail=$(jo firstname=Jan lastname=Fader)
```

```json
{
   "name": "jf",
   "id": 13,
   "parser": false,
   "detail": {
      "firstname": "Jan",
      "lastname": "Fader"
   }
}
```

## Filtern und bearbeiten

jq erlaubt das Filtern und Bearbeiten, aber die Syntax finde ich zu
kompliziert.

Daher kommt [gron](https://github.com/tomnomnom/gron) zum Einsatz. Mit diesem
klopft mensch das JSON flach, so dass es mit üblichen Shell-Tools (z.B. sed, grep
oder awk) bearbeitbar ist.

Nimmt man das oben mit jo erstellte Beispiel und verarbeitet es mit gron erhält
man folgende Ausgabe:

```bash
json = {};
json.detail = {};
json.detail.firstname = "Jan";
json.detail.lastname = "Fader";
json.id = 13;
json.name = "jf";
json.parser = false;
```

Mit gron -u kann man es nach der Bearbeitung dann wieder in JSON umwandeln. Bei
mir kommt da häufig dann eine Pipe-Kette aus curl, gron, sed/grep, gron -u zum
Einsatz.
