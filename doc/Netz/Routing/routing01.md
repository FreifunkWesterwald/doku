# BGP Konzentrator (Routing 01)

## Wie funktioniert unser Routing?

Wir können unseren Traffic beim AS 201701 vom Freifunk Rheinland e.V abkippen.

Wir haben folgende Netz bekommen:
* 185.66.195.84/31
* 2a03:2260:200a::/48

## Tunnel

Derzeit haben wir Tunnel nach DUS, FRA und BER. FRA ist derzeit nicht eingerichtet. Diese Tunnel werden mit GRE realisiert.

## BGP
Um unsere IP zu Announcen ist zwischen dem FFRL und uns pro Tunnel eine BGP Session konfiguriert. Auf der routing01 announcen wir derzeit nur IPv4 mit der IP 185.66.195.85/32.

## Routing für [Supernode Legacy](../Supernode/legacy.md)
Alle Pakete die derzeit von der 172.16.1.200 kommen werden auf die 185.66.195.85 genatted und über einen der Tunnel verschickt.
