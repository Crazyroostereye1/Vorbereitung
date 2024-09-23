---
tags:
  - netzwerke
  - Abschluss
  - Übung
---

# Networking
## IPv6
IPv6 wird in Hexadecimal (basis 16). 0-9 A-F
Die Länge einer IPv6 sind 128b mit 16b blöcken (4 Charakter), trennung mit :

| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | A   | B   | C   | D   | E   | F   |
### Präfix
Standard ist das Präfix 64b lang.
#### Standard
**Internet**
Präfix: *2001:0db8*

**Link-Local**
Präfix: *fe80::/10*
Präfix wenn nicht ins Internet geroutet wird nur im Lokalen Netz

**Unique-Local**
Präfix: *fc00::/7*
Für IPv4 ähnliche Local Adress aufbau

**Mulitcast**
Präfix: *ff00::/8*
Senden eines Packets an mehrer definierte Endgeräte

**Site-Local**
Präfix *fec0::/10*
### Kürzen
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

### Subneting
