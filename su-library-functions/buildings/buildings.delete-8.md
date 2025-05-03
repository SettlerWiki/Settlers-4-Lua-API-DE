---
description: 'SU Library: erst ab Version 0.3.0 verfügbar!'
---

# SU.Buildings.SetProduction

## SU.Buildings.SetProduction(buildingID, goodType, amount)

Gibt dem durch die ID angegebenen Gebäude den Auftrag, eine spezielle Anzahl an Waren herzustellen.

#### Notiz

* die KI stellt die Produktion der Waffenschmiede alle paar Sekunden um, somit ist diese Funktion **bei aktivierten KIs** momentan ziemlich **sinnlos**!
* funktioniert nur bei **Waffen- und Werkzeugschmieden**
* Spezialwaffen werden automatisch dem Volk entsprechend interpretiert, bspw. stellt ein Funktionsaufruf für Wikinger mit `Goods.BLOWGUN` automatisch Äxte ein, bei Römern Schwerter.

#### Parameter

* `buildingID`: ID des Gebäudes
* `goodType`: [goods.md](../../api-enums/goods.md "mention")
* `amount [0-100]`: Anzahl, die **addiert** wird! (0=zurücksetzen, 100=unendlich)

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude diese Ware nicht produzieren kann!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.SetProduction(buildingID, Goods.SWORD, 5)
```
