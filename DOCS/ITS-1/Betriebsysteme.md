---
tags:
  - BS
  - its-1
  - betriebsystem
  - os
---
Unter einem Betriebssystem versteht man eine Computer mit dem Kernal und allen wichtigen Systemkomponenten.
# Kernal

## Resourcenverwalltung
Resourcenverwaltung ist zuständig die richten Resourcen and die richte programme zu geben, und verhiindern das Applikation zuviel oder die selben Resourcen wie eine ander, zu beziehen.

Die Resourcenverwaltung beihaltet:
- **Prozessorverwaltung**
  Diese kümmert sich das eine Applikation ein oder meher Kern/Threads kriegt für ein gewiese zeit
- **Speicherverwaltung**
  Kümmert sich das jede Applikation genügend Arbeitsspeicher kriegt und sie sich nicht gegenseit den Arbeitsspeicher klauen und überschreiben.

*Fun Fact: RAM bedeutet `Random Access Memory`, welches bedeutet das alle Speicher median wo man auf jeglichen punkt indem Speicher zugreifen kann. Das heißt das SSD Speicher laut der Definition RAM ist*


### Ressourcen Konflikt
Der Ressourcen Konflikt ist der Fall wenn zwei Applikation die selben Ressourcen haben will und daher sich entgegenstoßen.

# Schichten
![OS Schicheten](Betriebsysteme_1.png)
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
