---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.RecruitVehicle

## SU.Buildings.RecruitVehicle(buildingID, vehicleType, amount)

Gibt bei dem mit der ID angegebenen Gebäude Fahrzeuge/Schiffe in Auftrag.

#### Parameter

* `buildingID`: ID des Gebäudes
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention")
* `amount [0-100]`: Anzahl der zu bauenden Fahrzeuge/Schiffe (100=unendlich)

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude keine Fahrzeuge/Schiffe produzieren kann!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.RecruitVehicle(buildingID, Vehicles.FERRY, amount)
```
