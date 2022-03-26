---
title: "Best Practices Projekte"
date: 2022-03-26T13:22:15+01:00
draft: false
---

In diesem Blogpost geht es um meine grundlegende Erfahrungen in der
Systemadministration, im System Engineering und hilfreiche Dinge dabei. Diesmal
nicht oder nicht überwiegend technisch, sondern organisatorisch bzw. auf
Projektebene.

Im Rahmen von Projekten bin ich immer wieder darauf gestossen, dass manche auch
komplizierten oder komplexen Projekte funktionieren und andere nicht und ich
habe mich gefragt warum. Bei einer Meta-Retrospektive haben sich die folgenden
Massnahmen und Punkte herauskristallisiert die einen starken Einfluss auf den
Projekterfolg haben.

Aus meiner Sicht greifen diese sowohl für Projekte alleine und private
Projekte wie auch für Projekte als Team und im Arbeitsumfeld.

## Vom "Big Picture" zu einzelnen Komponenten

Projekt bestehen grundsätzlichen aus mehreren Todos. Die meisten sogar aus
mehreren Komponenten oder Systemen.

Nehmt ein Blatt Papier oder eine Software und zeichnet das zu erstellende
System mit seinen einzelnen Komponenten auf. Versteht unbedingt den gesamten
Ablauf und nicht nur die einzelne Komponente die ihr umsetzen müsst.

Damit könnt ihr dann jederzeit, auch wenn ihr tief in einer einzelnen
Komponente steckt oder stress habt, einen Blick auf das grosse Ganze werfen und
es leistet für eine spätere Übergabe an ein Betriebs-, ein Support-Team oder
eure Nachfolgerin sehr gute Dienste.

## Todo- und Zeitverwaltung

Es ist völlig egal ob ein Ticketsystem (wie Redmine, JIRA, usw...), ein
physisches oder digitales Kanban-Board oder ein Papierjournal zum Einsatz
kommt. Aber es braucht eine (!) zentrale Stelle an der alle Todos abgelegt und
verwaltet werden.

Das Big Picture lässt sich super in einzelne Aufgaben aufteilen und dabei auch
die Komplexität, Priorität und evtl. Abhängigkeiten dieser bewerten.

Schätzt am Anfang des Projektes grob die einzelnen Projektkomponenten ab und
notiert das. Schätzt auch Aufgaben jeweils bevor ihr anfangt grob ab und
notiert das bei der jeweiligen Aufgabe.

Notiert die aufgewendete Zeit je Aufgabe, damit ihr einen guten Vergleich
zwischen geschätzter und aufgewendeter Zeit habt.  Wenn ihr merkt, dass ihr
euch dem Ende eurer Schätzung nähert und euch die Zeit ausgeht, fragt
rechtzeitig um Unterstützung im Team an oder eskaliert (falls ihr das könnt).

Fangt nicht mehrere Aufgaben an, sondern arbeitet an einer und schliesst diese
ab bevor ihr mit einer neuen beginnt. Multitasking funktioniert nicht, auch
wenn man glaubt es zu können. Nachweislich sinkt die Qualität und auch die
Durchlaufzeit der einzelnen Aufgaben.

## Dokumentation

Auch hier gilt: Es gibt nur einen Ort für Dokumentation. Welche Lösung benutzt
wird ist sekundär. Ob Mediawiki, Dokuwiki, Asciidoc, LaTeX oder sonstwas ist
wirklich egal.

Beginnt früh im Projekt mit der Dokumentation. Wenn es im ersten Schritt auch
mal nur Rumpfdokumente oder eine Sammlung an Befehlen oder Links zu externen
Dokumentation ist, dann ist das okay und definitiv besser als keine
Dokumentation.

Denkt bei der Dokumentation auch an eine mögliche Analyse bei Fehlern oder
Fallstricke für den Betrieb und denkt daran, dass jemensch anderes oder euer
zukünftiges ich nicht mehr so tief im Projekt steckt wie ihr gerade.
Dokumentiert also lieber zu viel und auf zu niedrigem Level als andersrum.

Sitzungen und Telefonate oder Absprachen (auch mit einem selbst): unbedingt
schriftlich festhalten und allen Teilnehmer\*innen zur Verfügung stellen.
Vielleicht das Protokoll auch gemeinsam (z.B: in einer kollaborativen Software)
schreiben, dann sind alle beteiligt.

## Zeitmanagement

Auch beim Zeitmanagement hilft eine Planung vom Groben zum Feinen. Es hilft
eine Liste von Aufgaben auf Monatsebene zu haben und diese dann wochenweise
herunterzuplanen.

Plant die nächste Woche am Freitagabend oder am Montagfrüh. Plant dabei:

- alle Sitzungen/Telefonate und fixen Termine ein.
- genug Blockzeiten für das Projekt ein.
- genug Zeit für Dokumentationsaufgaben ein.
- genug Zeit für Unvorhergesehenes ein.

Seid in Blockzeiten nicht erreichbar, sondern arbeitet am Projekt und zwar an
einer konkreten Aufgabe. Die E-Mails, der Gruppenchat oder andere Aufgaben
können warten.

Mir persönlich hilft es sehr, dass Handy in einen anderen Raum zu legen. Man
glaubt garnicht wie sehr die physische Hürde des Aufstehens einen von einem
"nur mal schnell" aufs Handy schauen abhält.

Macht nicht alles auf den letzten Drücker kurz vor Termin. Da kommt vermutlich
etwas was dazwischen und bei den "Allnightern" leidet die Qualität und es zehrt
an einem.

## Vorgehen/Debugging bei Fehlern oder Problemen

Wenn ihr im Projekt auf Fehler stosst, dann hangelt euch an folgendem Vorgehen lang:

1. Welche Komponente ist betroffen?
1. Welche Server oder welche Server sind betroffen?
1. Seid wann tritt der Fehler auf?
1. Lässt sich die Komponente einzeln testen?
1. Gibt es eine Logdatei der Komponente? Falls ja, was sagt das Logfile.

## Regeln

Gebt euch selbst als Einzelperson oder als Team Regeln für die Zusammenarbeit,
schreibt sie auf und haltet euch daran.

Lasst aber auch mal fünf gerade sein, wenn ihr euch nicht daran haltet. Wir
sind alle Menschen und keine Computer und das nächste Mal klappt es wieder.
Kein Grund sich schlecht zu fühlen oder nichts mehr zu tun.

## Leseempfehlungen

Diese Bücher waren für mich sehr hilfreich, auch wenn diese sich teilweise auf
Systemadministration oder Software-Projekte beziehen, ist vieles davon auch für
Projekte in anderen Bereichen gut nutzbar. Mir helfen die Punkte auch bei
mehreren privaten Projekten (z.B. Umzug oder Scheidung).

- Getting Things Done von David Allen
- Zeitmanagement für Systemadmistratoren von Tom Limoncelli
- The Phoenix Project
- The Unicorn Project

## Fazit

Vermutlich könnte man zu jedem der Abschnitte einen eigenen Blogpost verfassen,
"aber das ist eine andere Geschichte und soll ein andermal erzählt werden."
