---
tags:
  - BS
  - its-1
  - betriebsystem
  - os
  - kernel
---
Unter einem Betriebssystem versteht man eine Computer mit dem Kernal und allen wichtigen Systemkomponenten.
# Kernel

## Resourcenverwalltung
Resourcenverwaltung ist zuständig die richten Resourcen and die richte programme zu geben, und verhiindern das Applikation zuviel oder die selben Resourcen wie eine ander, zu beziehen.

Die Resourcenverwaltung beihaltet:
- **Prozessorverwaltung**
  Diese kümmert sich das eine Applikation ein oder meher Kern/Threads kriegt für ein gewiese zeit
- **Speicherverwaltung**
  Kümmert sich das jeded Applikation genügend RAM kriegt und sie sicht nicht gegenseit das RAM klauen und überschreiben.

### Resourcenkonflikt
Der Resourcenkonflikt ist der Fall wenn zwei Applikation die selben Ressourcen haben will und daher sich entgegenstoßen.

# Schichten
![[Betriebsysteme_1.png]]
# Eigenschaften
## Multitasking
Bedeutet das der Rechner aus Anwendersicht Mehrer Programme gleichzeitig verarbeiten kann. 
## Schedualing
Der Scheduler regelt die die zeitliche Ausführung
mehrerer Prozesse in Betriebssystemen.
Er teilt dem Prozessor mit, wann welcher
Prozess auszuführen ist.
Jeder Prozess wird nach einer bestimmten
Abarbeitungszeit unterbrochen (Zeitscheibe,
time slice). Dann ist der Prozess inaktiv und ein
anderer Prozess wird aktiv. Erhält er wieder eine
Prozessorzuteilung, so ist er wieder aktiv und
setzt seine Arbeit fort.
Meistens haben alle Zeitscheiben die gleiche,
feste Dauer. Über eine variable Zeitzuteilung
können Prozesse priorisiert werden.

## Mehrprozessorbetrieb
Dieser beschreibt die fähigkeit mehere Prozossorenkerne bzw. Prozzessorren

# Übungen

## 1
Ein OS besteht aus unterschiedlichen Schichten. 
Diese schichten sind die Hardware schicht, worin sich die Physische hardware deines Systems befindet.

Danach gibts die Kernal schicht worin sich die Treiber und Systemkritsche Software stücke befinden wie zum Beispiel Dateisystem

Nun kommen wir zur Userspace (Anwendungsschicht) worin sich alle Benutzerbezogenen Programme sich befinden.

## 2

## 3
API - Aplication programming Interface
Eine Schnittstelle um mit komponenten des OS zu agieren.
## 4
Der Resourcenverwalter tut zum Beispiel verwalten das das Ram schwere Videospiel genügend ram kriegt und verhindert das der Web Browser nich zu viel nimmt um das Spiel zu limitieren

##  5
Der Reourcenkonflikt ist wen zwei Programme auf die Selbe Resource Zugreifen will