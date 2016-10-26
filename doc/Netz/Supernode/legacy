# Supernode LEGACY

Legacy wurde aufgebaut um das Netz von der Gyros auf unsere [Proxmox Umgebung](../proxmox.md) zu migrieren, da die alte VM einen sehr kurzen aber harten Tot starb.


## VPN
Um die Last auf verschiedene Kerne zu verteilen wurden 4 fastd's installiert:


* wwVPN = Westerwald = Port 10009
* nrVPN = Neuwied = Port 10005
* lmVPN = Limburg = Port 10001
* akVPN = Altenkirchen = Port 10013

Diese werden auf der B.A.T.M.A.N Interface bat0 gebunden

````
post-up         /usr/sbin/batctl -m bat0 if add $IFACE
````

## INET Exit
Für das Internet wird der Traffic über die Routing Table 61 (enthält nur eine Defaultroute auf den BGP Konzentrator) geleitet.

````
ip route show table 61
default via 172.16.1.110 dev eth1

````

Damit für den späteren Split von den Communities auf einzelne VM's keine Routingprobleme entstehen, werden alle Pakete die über eth1 rausgehen auf die Interne IP der Legacy genatted (172.16.1.200)
