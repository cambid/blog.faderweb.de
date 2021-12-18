---

date: 2008-11-04 18:12:43+00:00
draft: false
title: Einfache Browserstatistik

url: /2008/11/04/einfache-browserstatistik/
categories:
- (Auf-)Gelesen
- Linux
---

Ich wollte heute einfach mal nur wissen mit welchen Browsern die Leute auf meine und ein paar andere Website gehen. Klar kenne ich visitors, awstats, webalizer, aber die muss man alle als CGI laufen lassen und die liefern auch viel zu viel Statistiken (Visits, Page, Google-Schlagworte, Referer, usw.) waren mir also für diese kurze Statistik zu viel Aufwand.

Schlussendlich hab ich browsercounter gefunden. Es ist ein einfaches perl-Skript, dass auf der Kommandozeile aufgerufen wird und hübsche Auswertungen aus einem oder mehreren access.log-Dateien des Indianers (apache2) generiert. Die Auswertungen lasssen sich sogar mit w3m auf der Konsole betrachten, die Logfiles dürfen auch mit gzip oder bzip2 komprimiert sein.

Nähere Infos und eine Beispielauswertung gibts unter: [http://snowhare.com/utilities/browsercounter.html](http://snowhare.com/utilities/browsercounter.html)
