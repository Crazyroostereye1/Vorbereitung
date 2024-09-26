---
tags:
  - its-1
---
# IPv6
[Dokumentation](DOCS/IPv6.md)

IPv6 wird in Hexadecimal (basis 16). 0-9 A-F
Die Länge einer IPv6 sind 128b mit 16b blöcken (4 Charakter), trennung mit :

| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | A   | B   | C   | D   | E   | F   |
## Präfix
Standard ist das Präfix 64b lang.
### Standard
**Internet**
Präfix: *2001:0db8*

**Link-Local**
Präfix: *fe80::/10*
Präfix wenn nicht ins Internet geroutet wird nur im Lokalen Netz.

**Unique-Local**
Präfix: *fc00::/7*
Diese Adresse wird verwendet man zwischen zwei verschieden private Netzwerke zu reden. Also im falle wenn man über einen Router gehen muss.

**Mulitcast**
Präfix: *ff00::/8*
Senden eines Packets an mehrer definierte Endgeräte

**Site-Local**
Präfix *fec0::/10*
## Kürzen
- 75f5:0826:018b:31d9:1575:cd7a:be86:76aa

**Einmal 0 Segment kürzen**: 
75f5:0826:**0000**:31d9:**0000**:cd7a:be86:76aa
-> 75f5:0826:**0**:31d9:**0**:cd7a:be86:76aa

**Zwei oder mehr aneinander 0 Semente kürzen**
75f5:0826:**0000:0000:0000**:cd7a:be86:76aa
-> 75f5:0826::cd7a:be86:76aa
*Hinweis:* Kann Nur einmal gemacht werden

**Eine 0 im Segemnt kürzen**
75f5:**0**826:0000:0000:0000:cd7a:be86:76aa
-> 75f5:**826**:0000:0000:0000:cd7a:be86:76aa

## Subneting
![IPv6_1](IPv6_1.png)
Bei der IPv6 subnet teillung differenzieren bei einem 16 Segment, 4 Charakter, 1 Bit.
Unter einem 16 Segement verstehen wir einer der 4 Charakter Länge Segmente:
	**eab7**:673e:10a4:**bbbf**:4183:e4a0:29b0:916e
Eine 4 Charakter:
	**e**ab7:673e:10a4:**b**bbf:4183:e4a0:29b0:916**e**
Eine bit ist ein bit.
Die nummern beschreiben jedes mal wieviel bits das sind.
Das heißt das wir bei einem Subnet der Größe 16,32,48,64 müssen wir jeweileig eine Segment hinzugeben oder entfernen.

Bei dem Subnetting in 4er Schritten heißt 4,8,12,16,20,... müssen wir jeweilig eine Charakter, also Buchstaben/Ziffer, entfernen oder hinzufügen.

Bei der Letzen, also der 1 Bit schritte, ist am schwersten. Dort musst du dich zum nächsten Character herantasten und daraufhin den betroffen Charakter in seine Bits aufteilen subtrahieren

### Beispiele
**16er Segmente**
eab7:673e:10a4:bbbf:4183:e4a0:29b0:916e /64
*eab7:673e:10a4:bbbf:: /64*
23c8:beab:659c:d965:af29:0e9f:b7f4:63dd /48
*23c8:beab:659c /48*
7086:1976:06ab:af17:4c4f:7e68:5233:2b20 /16
*7086 /16*
**4er Charakter**
eab7:673e:10a4:bbbf:4183:e4a0:29b0:916e /44
*eab7:673e:10a0:: /44*
23c8:beab:659c:d965:af29:0e9f:b7f4:63dd /60
*23c8:beab:659c:d960:: /60*
7086:1976:06ab:af17:4c4f:7e68:5233:2b20 /8
***70**00 /60*
**1er Bit**
eab7:673e:10a4:bbbf:4183:e4a0:29b0:916e /45
*eab7:673e:10a4 /48*
*eab7:673e:10a0 /44*
*eab7:673e:10a8:: /45*
1000 = 8
*8421*

23c8:beab:659c:d965:af29:0e9f:b7f4:63dd /33
*23c8:beab:659c /48*
*23c8:beab:8:: /33*
6
0110
1000

7086:1976:06ab:af17:4c4f:7e68:5233:2b20 /63
*7086:1976:06ab:af17 /64*
*7086:1976:06ab:af1e /63*
1111 (64) - 1
1110  (63)


**Aufgabe**

Ein Unternehmen hat den IPv6-Präfix `2001:0db8:85a3::/48` erhalten. Sie sollen diesen Präfix weiter in Subnetze unterteilen:

1. Bestimmen Sie den Präfix für die ersten zwei Subnetze, die jeweils eine Länge von /64 haben.
2. Welcher Bereich deckt das 50. Subnetz ab?
3. Geben Sie für alle drei Subnetze jeweils die erste und letzte mögliche IPv6-Adresse an.

---
1. Aufgabe 1
	1. `2001:0db8:85a3:0000:: /64`
	2. `2001:0db8:85a3:0001:: /64`
2. Aufgabe 2
	1. `2001:0db8:85a3:0032:: /64` 
	   Weil das Letzte Segment 0 ist und wir das 50st Subnetz haben wollen rechnen wir einfach die Decimal zahl 50 in Hex um.
3. Aufgabe 3
	1. `2001:0db8:85a3:0000:: /64`
		1. `2001:0db8:85a3:0000:0000:0000:0000:0001`
		2. `2001:0db8:85a3:0000:ffff:ffff:ffff:ffff`
	2. `2001:0db8:85a3:0001:: /64`
		1. `2001:0db8:85a3:0001::0001`
		2. `2001:0db8:85a3:0001:f:f:f:f`
	3. `2001:0db8:85a3:0032:: /64`
		1. `2001:0db8:85a3:0032::0001`
		2. `2001:0db8:85a3:0032:f:f:f:f`

