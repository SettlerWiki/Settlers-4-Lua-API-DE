---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetProductionPercentage

## SU.Buildings.SetProductionPercentage(buildingID, swords, bows, armors, racespecialweapons)

Gibt dem durch die ID angegebenen Gebäude den Auftrag, eine spezielle Anzahl an Waren herzustellen.

#### Notiz

* die KI stellt die Produktion der Waffenschmiede alle paar Sekunden um, somit ist diese Funktion **bei aktivierten KIs** momentan ziemlich **sinnlos**!
* die Summe der Waffen muss 100% ergeben
* die KI setzt ihre Waffenproduktion kontinuierlich selbst und überschreibt damit die hiermit gesetzten Werte immer wieder... Eine Funktion um dieses Verhalten deaktivieren zu können ist in Planung.
* **bei jedem Aufruf dieser Funktion werden interne Werte zurückgesetzt.** Dadurch wird als erstes Produkt immer die erste Waffe hergestellt, die nicht 0% zugewiesen hat. D.h., **wird diese Funktion kontinuierlich** (z.B. alle 5 Ticks) mit z.B. 1% Schwerter **aufgerufen**, werden **deutlich mehr als 1% Schwerter hergestellt**, da bei jedem Aufruf wieder 1 Schwert hergestellt wird! Eine Änderung der internen von S4 verwendeten Statistik ist in Planung...

#### Parameter

* `buildingID`: ID des Gebäudes
* `swords`: Prozent der zu produzierenden Schwerter
* `bows`: Prozent der zu produzierenden Bögen
* `armors`: Prozent der zu produzierenden Rüstungen
* `racespecialweapons`: Prozent der zu produzierenden Spezialwaffen (wird beim Römer und Dunklen Volk automatisch zu "swords" addiert)

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude diese Ware nicht produzieren kann!)
* 0: sonst / Fehler / Summe der Waffen nicht 100%

#### Beispiel

```lua
local success = SU.Buildings.SetProductionPercentage(buildingID, 10, 60, 0, 30)
```
