---
title: "Vim fortgeschrittene Navigation"
date: 2025-07-31T21:20:37+02:00
draft: false
tags:
- vim
- editor
---

Heute geht es um fortgeschrittene Kommandos in vim.

Beim letzten Mal ging noch eine wichtige Navigation vergessen:

- % springt zur öffnenden/schließenden Klammer

Hinweis: Für alle Kommandos findet man mit :help <commando> die jeweilige
Hilfeseite direkt in vim.

## Register und Makros

- Register: Mehrere Zwischenablagen. Mit "aY wird in das Register a kopiert,
  mit "ap daraus wieder eingefügt
- Makro aufzeichnen: qa zum Starten der Aufzeichnung in Register a, dann
  gewünschte Befehle eingeben, mit q beenden. Mit @a das Makro abspielen, mit
  @@ das letzte Makro wiederholen.
- :registers zeigt alle Register an

## Globale Kommandos

- Global-Befehl (:g): Führt einen Befehl auf alle Zeilen aus, die mit einem
  Muster übereinstimmen, z.B. :g/pattern/d löscht alle Zeilen mit „pattern“.

## Jumplist

- :jumps zeigt die Jumplist an
- CTRL+O und CTRL+I (springt rück-/vorwärts in der jumplist

## Magische globale Kommandos

- ga: Zeigt den ASCII-Wert des Zeichens unter dem Cursor.
- gu{motion} / gU{motion}: Macht Bereich kleingroß- bzw. großgeschrieben (z.B. gUw).
- gq{motion}: Textumbruch nach einer Bewegung (z.B. gqap für den aktuellen Absatz).
- gn: Wählt das nächste Suchergebnis aus (prädestiniert für schnelles Ersetzen).
- gf: Öffnet die Datei unter dem Cursor.

## Sprungmarken
- m[a-zA-Z] setzt eine Marke
- '[a-zA-Z] springt zur Marke. Kleinbuchstaben: innerhalb der Datei; Großbuchstaben: zwischen Dateien
- :marks zeigt alle Sprungmarken an
