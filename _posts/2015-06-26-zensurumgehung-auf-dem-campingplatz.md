---
title: Zensurumgehung auf dem Campingplatz
layout: post
tags:
  - Android
  - FOSS
  - Zensur
---
<u>Ausgangssituation</u>

Ich bin gerade auf einem Campingplatz auf dem es kostenloses WLAN gibt. Laptop habe ich bewusst keinen mit genommen, ich will schließlich abschalten. Ein Android-Smartphone (CyanogenMod 12; Android 5.0.2) muss reichen. Ich nutzte das Smartphone auch zum Download von Podcasts.

<u>Problem</u>

Das WLAN ist gefiltert. Zuerst viel mir das auf, als ich eine neue Folge [Logbuch Netzpolitik](http://logbuch-netzpolitik.de/) runter laden wollte. [AntennaPod](http://antennapod.org/) bricht den Download-Versuch nach ca. 3 Minuten und 1% Fortschritt ab. Ich dachte zuerst an eine schlechte WLAN-Verbindung, aber dem war nicht so. Aus dem PlayStore lassen sich App-Updates von mehreren 100 MB problemlos downloaden. Der Filter dreht mir also beim Download von großen Dateien den Hahn zu.

<!--more-->

<u>Lösung</u>

Die Lösung in solchen Fällen bietet praktisch immer [Tor](https://www.torproject.org/). Auf Android stellt [Orbot](https://guardianproject.info/apps/orbot) die Verbindung ins Tor-Netzwerk her, hier die Version 15.0.1 Beta3. Also schnell gestartet, doch der böse Filter schlägt auch hier zu, Orbot kann die "Directory Server" nicht erreichen.

<img src="/assets/2015/wpid-june-29-2015-120148-am-gmt-0200.jpg.jpg" alt="image"/>

Diese sind ein Verzeichnis von Eingangsknoten in das Tor-Netzwerk, ohne die Adressen dieser Server ist die Verbindung erst mal nicht möglich. Aber Tor bietet noch weitere Möglichkeiten eine Verbindung ins Netzwerk her zu stellen.
  
Die Einfachste bieten so genannte Bridges.
  
<img src="/assets/2015/wpid-june-28-2015-115701-pm-gmt-02001.png1_.png" alt="image" />

<img src="/assets/2015/wpid-june-28-2015-115740-pm-gmt-02001.jpg1_.jpg" alt="image" />

Komischerweise ist bridges.torproject.org nicht blockiert und ich bekomme 3 Adressen serviert.

Ich kopiere eine der 3 Zeilen vollständig und füge sie in Orbot in den Einstellung ein:
  
<img src="/assets/2015/wpid-june-29-2015-120318-am-gmt-0200.jpg.jpg" alt="image" />

Außerdem in muss man in den Einstellungen von Orbot noch den Haken bei "Use Bridges" setzen.

So und nun läuft die Sache auch:
  
<img src="/assets/2015/wpid-june-29-2015-120218-am-gmt-0200.jpg.jpg" alt="image" />
