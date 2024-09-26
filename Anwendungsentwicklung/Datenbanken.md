# Entity-Relationship-Diagrams (ERD)
## Zeichen der ER Diagramme

![[ERD-Index.excalidraw]]
Eine Tabelle hat mehrere Entitäten, diese sind Datenwerte wie z.B Name oder Adresse.
Zwischen mehren Tabellen kann ein Beziehung (Eng.: Relationship) existieren die in zwei Formen verbunden werden kann:
- 1 zu n 
- 1 zu 1
*`1` zu `n`*  beschreibt Das ein Eintrag der Tabelle sich auf viele Einträge in anderen Tabelle beziehen kann.
Eine *`1` zu `1`* dahingegen beschreibt **ein** Eintrag in der ersten Tabelle auf **ein** Eintrag in der anderen Tabelle
## Aufgaben


![[Programmieren_1.pdf#page=5]]
### Aufgabe 1 (4)
![[ERD.excalidraw]]

# SQL
## Datentypen
| Name         | Bedeutung     | Beispiel                           |
| ------------ | ------------- | ---------------------------------- |
| `int`        | Ziffer        | 1,2,3,4,...                        |
| `varchar(*)` | Zeichenkett   | haus,baum,hunderte,...             |
| `bool`       | Boolean       | 0,1,true,false                     |
| `date`       | Datum         | 01.02.2024, 03.03.2002             |
| `timestamp`  | Ein Zeitpunkt | 01.02.2024 14:31, 03.04.2024 16:21 |

## Syntax
| Syntax                                       | Beschreibung                                                                                                                                           |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SELECT                                       | Mit diesem Schlüsselwort beziehst du Gewisse Daten bei der Datenbank. Mann kann es auch mit einem * ersetzten um alle Felder Zu ziehen.                |
| FROM                                         | Definiert von welcher Datenbank du die Daten beziehen willst.                                                                                          |
| WHERE                                        | Bearbeitet eine Bedingung die die Daten die du Beziehst einhalten müssen                                                                               |
| JOIN \<*a*> ON \<*b*>.\<*c*> = \<*a*>.\<*d*> | Diese Aktion verbindet die genante Tabelle (*a*) auf der `FROM` Tabelle (*b*) mit der spalte (*c*) wo beim wert von Tabelle (*a*) mit der spalte (*d*) |



## Aufgaben

### Aufgabe 1 (5)
`KundenNr` -> `int`
`Kunde_Aktiv` -> `bool`
`PLZ` -> `varchar(5)`
`Telefonnummer` -> `varchar(20)`
`Erfasst am` -> `Date`
`IBAN` -> `varchar(50)`

### Aufgabe 2 (7)
```sql
SELECT COUNT(*)
FROM Kunde
WHERE Ort is 'Augsburg' 
AND Aktive = true;
```
### Aufgabe 3 (8)
```sql
CREATE TABLE Werbeaktion(
  WerbungsID int,
  Werbepartner varchar(50),
  Werbung_verschickt bool,
  KundenNr int,

  PRIMARY KEY (WerbungsID),
  FOREIGN KEY (KundenNr) REFERENCES Kunde(KundenNr)
)
```

### Aufgabe 4 (9)
```sql
SELECT COUNT(*)
FROM Werbeaktion w
JOIN Kunde k on k.KundenNr = w.KundenNr
WHERE w.Werbung_verschickt < '2021-12-31'
AND k.PLZ LIKE '8%' 
```

### Aufgabe 5 (10)
- Casandra
- MangoDB
