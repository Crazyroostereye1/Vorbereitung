---
tags:
  - vpn
  - its-2
  - netzwerke
---
# VPN

## Prozess der Kapselung
![[kapselug]]

## Arten von VPN
### Site-to-Site
*auch: Gateway-to-Gateway*

Diese VPN beschreibt eine Verbindung zwischen zwei Netzwerke aufbaut. Zum Besipiel von einem Standort und einem zweiten Standort. Das bedeuted das beide Netzwerke von beiden verbunden sind und über die VPN geroutet werden.

### End-to-Site
*auch: Host-to-Gateway*

Diese Art ist die Verbindung von einem einziegen Endgerätes z.B. Laptop, welches sich mit der VPN in ein anderes Netzwerkes verbindet. Das bedeuted das Netzwerk worin sich das Endgerät vom Physischen gerät nicht mit der Site verbunden ist.

### End-to-End
*auch: Host-to-Host*

Bei einer End-to-End verbindung werden zwei Endgeräte miteinander verbunden. Das heißt das es nur mit dem jeweiligen Endgerät sich verbinden kann.
## VPN Protokolle
### IPSec
![[EtE-vpn]]

---
**R1**
äußerster IP-Header
	-> Destination IP-Adresse
		`18.20.6.4`
	-> Source IP-Adresse
		`18.20.5.3`

innerer IP-Header
	-> Destination IP-Adresse
		`10.10.100.1`
	-> Source IP-Adresse
		`192.168.0.1`