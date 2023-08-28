---
title: "Vim navigieren"
date: 2023-08-28T20:03:37+02:00
draft: false
tags:
- vim
- editor
---

Heute geht es um ein paar spannende Navigationskommandos in Vim.

## zeichenweise

Zeichenweise Navigation kennt man von anderen Editoren. Auch in Vim geht das
mit den Pfeiltasten.

Noch besser und mit mehr Vorteilen geht es wie folgt:
- nach links: h
- nach rechts: l
- nach unten: j
- nach oben: k

## Wortweise

Vim kennt zwei verschiedene Arten von Wörtern: Word und WORD. Bei WORD trennt
es nur anhand von Leerzeichen/Tabs/Zeilenenden. Word ist definiert als eine
Folge von Buchstaben, Zahlen, Unterstrichen getrennt mit
Leerzeichen/Tabs/Zeilenenden.

[Mehr Details inkl. Beispielen](https://dcchuck.github.io/vim/2016/08/14/vim-words.html)

Die folgenden Kommandos gibt es jeweils in Gross- (für WORD) und Kleinschreibung (für Word)

- wortweise nach vorne: w, W
- wortweise nach hinten: b, B
- zum Ende des aktiven Wortes: e, E

## satz- oder absatzweise

- Springe zum nächsten oder vorherigen Satz: ( oder )
- Springe zum nächsten oder vorherigen Absatz: { oder }

## innerhalb der Zeile

- in der Zeile:
  - 0 geht zum ersten Zeichen in der Zeile.
  - ^ geht zum ersten nicht leeren Zeichen der Zeile.
  - $ geht zum Ende der Zeile.
  - g_ geht zum letzen nicht leeren Zeichen der Zeile.

- suchend in der Zeile:
  - fx geht nach rechts in der Zeile bis x. Der Cursor landet auf dem x.
  - Fx geht nach links in der Zeile bis x. Der Cursor landet auf dem x.
  - tx geht nach rechts in der Zeile bis zu x. Der Cursor landet auf dem Zeichen davor.
  - Tx geht nach links in der Zeile bis zu x. Der Cursor landet auf dem Zeichen danach.

- zu einer bestimmten Spalte in einer Zeile: 15| geht zur 15ten Spalte in der Zeile.

## zeilenweise

- zu einer bestimmten Zeile springen: 15gg oder :15
- letzte Zeile: G
- erste Zeile: gg
- prozentual: {percent}% geht zu x Prozent der Datei.

## bildschirmweise

- runterscrollen: CTRL-D
- hochscrollen: CTRL-U

## Multiplikatoren

Fast alle der obigen Kommandos lassen sich mit einer vorgestellten Zahl
multiplizieren. Beispielsweise bringt 5w den Cursor 5 Wörter weiter oder 3{
bringt den Cursor drei Absätze zurück oder 5j bringt den Cursor fünf Zeilen
nach unten.

## Ausblick

Diese Navigationskommandos lassen sich auch mit weiteren Aktionen kombinieren
und bilden daher eine wichtige Grundlage für die effektive und effiziente
Nutzung von Vim.
