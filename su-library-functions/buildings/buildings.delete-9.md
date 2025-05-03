---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetProductionPercentMode

## SU.Buildings.SetProductionPercentMode(buildingID, enable)

Gibt dem durch die ID angegebenen Gebäude den Auftrag, in oder aus dem Prozente-Modus zu wechseln.

#### Notiz

* die KI stellt die Produktion der Waffenschmiede alle paar Sekunden um, somit ist diese Funktion **bei aktivierten KIs** momentan ziemlich **sinnlos**!

#### Parameter

* `buildingID`: ID des Gebäudes
* `enable [0-1]`: 0 deaktiviert, 1 aktiviert den Prozente-Modus beim Gebäude

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude keine Ware produzieren kann!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.SetProductionPercentMode(buildingID, 1)
```
