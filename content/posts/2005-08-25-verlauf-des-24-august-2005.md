---

date: 2005-08-25 00:30:00+00:00
draft: false
title: Verlauf des 24. August 2005

url: /2005/08/25/verlauf-des-24-august-2005/
---

Hallo Leute,
heute hab ich bis auf das letzte Tabellenblatt und einige Anpassungen die Tabelle fuer den 14.ten Info endlich fertig gestellt.

Da waren richtig komplexe Zusammenhaenge drin. Zum Beispiel musste folgende Funktionalität in Excel eingebaut werden. Man verzeihe mir die boese Mischung von BASH, C++ und einfachen Sätzen, aber so kann ich mir Zusammenhaenge leichter vorstellen.

    
    
    <code>
    SUMME=0
    for i in AU AV AW AX AY
    do
    if [ Wert in Spalte $i und Zeile 7 (z.B: AU7) -eq 0 ];then
        SUMME+= Wert in Spalte $i und Zeile 3
    fi
    


`
Die Loesung war eine Kombination aus SUMME und mehreren WENN-Funktionen.

    
    =SUMME(WENN(AU7=0;AU3;0);WENN(AV7=0;AV3;0); ... )

eigentlich doch ganz einfach, oder?

Heut abend hab ich mich noch mit Steffen getroffen. Wir haben erstmal was gegessen und uns dann gemuetlich vor die X-Box gesetzt und den ganzen Abend gezockt. Ich hab jetzt noch schmerzen im linken Daumen.

Auf Bald
