---
tags:
  - IPv6
  - netzwerke
---
# IPv6
IPv6 ist die neuste Version vom Internet Protocol (version 6). Es wurde in 1998 als ein Entwurf be IETF aufgenommen. Die Entwicklung davon hat begonnen um ein erwartetes Problem zu Lösen, das Problem vom Adress Ende von der IPv4 addresse. 
In 2017 wurde der Standard ratifiziert.

Der Besonderheit von IPv6 über IPv4, is das es 128 bit verwendet gegenüber den 32 bit. Das ändert die Anzahl von möglichen Addressen von $2^{32}$ was ca. 4 Millarden sind zu $2^{128}$ eine Zahl wo ich gerade nicht die Worte habe.

## Aufbau
Der Aufbau einer Adresse besteht aus dem Präfix und dem Interface Bereich.

Der Präfix Bereich besteht aus zwei teilen, dem Site Präfix und dem Subnet. Der Site Präfix beschreibt ob es im link-local

Das *Site Präfix* beschreibt sind die [Spezielle Adressbereiche](#Spezielle%20Adressbereiche), also Site-Local, Global Unicast, etc., und der Subnet teil. Der Subnet teil wird von dir (Administrator) definiert.

Der *Interface Bereich* ist die direkte Adresse vom Gerät selber.

![](assets/ipv6.png)

## Spezielle Adressbereiche
### Link-Local Unicast
*Adressbereich:* `fe80::/64`
Netwerke mit diesem Bereich werden nur in einem Geschlossen Netzwerksegments Gerouted. In Einfach wir es nur bis zum ersten Router gerouted und das wars.

### Site Local Unicast
*Adressbereich:* `fec00::/10`
Mit diesem Site Präfix beschreibt das Lokale Netz ähnlich wie das Privates Netz in IPv4 (192.168.0.0). Alle Adressen mit diesem Präfix werden nur innerhalb der Organisation gerouted.

### Unique Local Unicast
*Adressbereich:* `fc00::/7`
Dies wird verwendet um zwischen zwei angeschlossen Netzwerke zu kommunizierne also zwischen zum Beispiel zwei Separierte Organisations Netze die über ein Router verwendet werden.

### Multicast
*Adressbereich:* `ff00::/8`
Der Multicast ist ähnlich wie bei *IPv4* womit man mehrere Clients gleichzeitig erreichen will. Wie das erzielt wird ist durch das verwenden von speziellen *Flags*:
**Erster Charakter:**
ff**0**0

| Flage | Beschreibung                                        |
| ----- | --------------------------------------------------- |
| 0     | Permanent definierte Adressen (von der IANA)        |
| 1     | Transient oder dynamisch Adressen                   |
| 3     | Unicast Präfix basierte Adresse                     |
| 7     | Multicast Adressen welche den Rendezvozs Points hat |
**Zweiter Charakter:**
ff0**0**

| Flage | Beschreibung                                                                                                                                       |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Interfacelokal (Loopback)                                                                                                                          |
| 2     | `link-local` werden, alles wird im Lokalen Netz. Verlässt nie das subnetz                                                                          |
| 4     | `adminlokal`, Adressen welche vom Router als speziell makiert sind                                                                                 |
| 5     | `sitelokal`,  können vom Router gerouted werden, aber nicht an boarders                                                                            |
| 8     | `organisationlokal`, diese werden auch an Border Routern weitergeleitet werden aber nur innerhalb dem "*Unternehmen*" (wir im Router Konfiguriert) |
| e     | `gloabaler Multicast`, wird überall gerauted                                                                                                       |
0,3,f sind reserviert
alle restlichen ziffern können frei belegt werden vom Administrator

### Globaler Unicast
*Adressbereich:* `2000::/3`
Das sind alle Adressen die im Globalen Internet verwendet. Dort versteht man `2001::` bezieht sich auf das Internet. Dort versteht man aber `2001:0db8:: /32` für standard Internet adressen verwendet wird. 

## Verkürzen
Wie wir schon vorhin gesehen haben werden IPv6 Adressen in Hexidecimal geschrieben. Das Bedeuted es hat 16 ziffern (1 bis F).
Weil das Bei 128 immer noch ziemmlich viele Charaktere (32). Diese werden dann noch in 4 Charakteren oder 16 Bit Segmenten Aufgeteilt. Um es zu vereinfachen das zu lesen kann man unter umftänden es verkürzen besonder im fall von 0.

### `0000` zusammenfassen
Wenn in einer IPv6 ein Segment nur `0` (also `0000`) kan es zur einer einzigen `0`zusammengefasst werden.

**Beispiel:**
``1733:5829:0000:6805:0000:7a04:e03c:0d1d``
wird zu
``1733:5829:0:6805:0:7a04:e03c:0d1d``

### Mehrere 0 Segmente zusammenfassen
Wenn Mehrere 0 Segmente aufeinander folgen können die zusammengefasst werden mit einem `::`. Diese Aktion kann aber nur einmal in der IP Adresse gemacht werden.

**Beispiel:**
``1733:5829:0000:0000:0000:7a04:0000:0000``
wird zu
``1733:5829::7a04:0000:0000``
***!!!Es geht nicht es mehrmals zu machen!!!***
DAS GEHT NICHT:
``1733:5829::7a04::``
Sonder wäre:
``1733:5829::7a04:0:0`` oder ``1733:5829:0:0:0:7a04::`` 

