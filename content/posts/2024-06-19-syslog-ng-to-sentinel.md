---
title: "Syslog-ng to MS Sentinel via CEF"
date: 2024-06-19T17:07:37+02:00
draft: false
tags:
- it
- microsoft
---

## Einleitung

Microsoft hat mit [Microsoft
Sentinel](https://learn.microsoft.com/de-de/azure/sentinel/overview?tabs=azure-portal)
eine cloudnative SIEM-Lösung im Angebot. In einem SIEM will man aber auch Logs
und Meldungen von Nicht-MS-Geräten haben (z.B. von Ubiquiti-Accesspoints oder
Linux-Servern). Microsoft bietet hierzu div. Connectoren an um andere Formate
anzunehmen. Unter anderem einen Connector im Common Event Log Format (CEF).

Ein Überblick des Setups mit einer Linux-VM mit syslog-ng zum Einsammeln und
Weiterleiten der Meldungen an Microsoft Sentinel findet sich unter
[Overview](https://learn.microsoft.com/en-us/azure/sentinel/cef-syslog-ama-overview?tabs=single)

Das Vorgehen zur Installation findet sich unter [Connector im Common Event Log
Format](https://learn.microsoft.com/en-us/azure/sentinel/connect-cef-syslog-ama?tabs=portal).

Das CEF-Format selbst ist unter
[1](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors-8.3/cef-implementation-standard/Content/CEF/Chapter%201%20What%20is%20CEF.htm)
und
[2](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors-8.3/cef-implementation-standard/Content/CEF/Chapter%202%20ArcSight%20Extension.htm#_Toc494359739)
gut dokumentiert.


## Konfiguration

Die Konfiguration um die im Syslog-Format ankommenden Logs in CEF zu
konvertieren und dann an den Azure Monitor Agent (AMA) weiterzugeben kann in
/etc/syslog-ng/conf.d/ unter Debian oder Ubuntu abgelegt werden.

Hier ein funktionales Beispiel mit teilweise noch fixen Werten in manchen Feldern.

```
template CEF {
    template("$DATE $SOURCEIP CEF:0|Ubiquiti|Networkstuff|1.0|DeviceCLassID|$MSG|1|msg=$MSG\n");
    template_escape(no);
};
destination d_azure_mdsd {
        network("127.0.0.1"
        template(CEF)
        port(28330)
        flags(no_multi_line)
        log-fifo-size(25000));
};

log {
        source(s_src); # will be automatically parsed from /etc/syslog-ng/syslog-ng.conf
        destination(d_azure_mdsd);
        flags(flow-control);
};
```

Danach muss der syslog-ng einmalig neu gestartet werden:

```bash
systemctl restart syslog-ng
```

Die möglichen Variablen im Template sind unter
[Macros](https://axoflow.com/docs/axosyslog-core/chapter-manipulating-messages/customizing-message-format/reference-macros/)
dokumentiert und die Verwendung von Template-Funktionen unter [using template
functions](https://axoflow.com/docs/axosyslog-core/chapter-manipulating-messages/customizing-message-format/reference-macros/)

## Debugging

Um zu prüfen in welchem Format der syslog-ng die Daten an den AMA weitergibt,
kann der unverschlüsselte lokale Netzwerktraffic mitgelesen werden:

```bash
tcpdump -i any port 28330 -A -l -s 65535
```
