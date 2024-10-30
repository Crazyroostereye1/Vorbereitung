# Verschlüsselung
## Die 3 Grundsätze der IT-Sicherheit
- Vertraulichkeit
- Integrität
- Authentizität

## Asymmetrische Verschlüsselung
In der Asymmetrischen Verschlüsselung besteht aus zwei Kryptographischen Schlüssel. Einen Private Key und ein Public Key. Funktional sind die Schlüssel Identisch. Der Unterschied ist das wir sie anders behandeln in der Kommunikation.

Das Verfahren eine Nachricht verschlüsselt zu senden, wäre den Empfänger anfragen mir seinen Public Key zu senden.
Mit diesem Key verschlüssele ich meine Nachricht, welche er nur wieder mit seine Private Key entschlüsseln kann. 
Als Zusatz kann ich, um zu verifizieren das es von mir kommt (*Authentizität*), erstell ich eine Hash meiner Nachricht und verschlüssel diesen Hash mit meine Private Key. Dieses ermöglicht jeder der meine Public Key hat diesen Hash zu lesen, aber verifiziert das die Nachricht von mir kommt.

**Erstellen einer MAC**
```mermaid
flowchart TD
Start --> hs(Erstell Hash von meinem Dokument)
hs --> MAC(Verschlüssele Hash mit meinen Privat Key)
MAC --> erg(Mac erschaffen)
```
**Ablauf einer Asymmetrischen Kommunikation mit MAC**
*Teilnehmer 1 sendet Nachricht and Teilnehmer 2*
```mermaid
sequenceDiagram
Teilnehmer 1 ->> Teilnehmer 2: Tauschen Public Keys aus
Teilnehmer 1 ->> Teilnehmer 2: Verschlüssele Nachricht mit Pub Key von T2 und hänge MAC dran
```
### Probleme
- Sehr Resourcen Intensive
### Veschlüsselungs Algorithmen
- RSA
- ECC

## Symmetrische Verschlüsselung
Die Symmetrische Verschlüsselung ist hingegen weitaus einfacher. Es gibt ein Schlüssel der Ver- und Entschlüsselt. Der nachteil davon ist man muss iregenwie den Schlüssel dem Teilnehmer sicher übergeben

## Hybride Verschlüsselung
In der Hybriden verwenden wir beide sorten der Veschlüsselung. Diese ist am häufigsten verwendete form der Verschlüsselung, da sie leicht, sicher und Resourcen Effizent ist in der Kommunikation.

### Ablauf

```mermaid
sequenceDiagram
T 1 -> T 2: Austausch der Public Keys
T 1 -> T 2: Genierer Symmetrischen Schlüssel
T 1 ->> T 2: Verschlüsselt mit dem Pub Key von T2 einen Sym Schlüssel
T 2 ->> T 1: Sende Nachricht mit Verschlüsselt mit Sym Schlüssel
```
## Digitales Zertifikat nach X.509
```mermaid
sequenceDiagram
Client ->> Server: Session Request
Server ->> Client: Sends X.509 Certificate with public Key
Client --> Server: Checks Certificate with known Certificates Autorities (CA)
Client ->> Server: Client generates Sym Key sends it Encrypted with Pub Key
Client -> Server: Client and server communicate with Sym Key 
```
