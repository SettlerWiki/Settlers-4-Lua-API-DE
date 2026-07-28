---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Vehicles.DeleteVehiclesInArea

## SU.Vehicles.DeleteVehiclesInArea(playerID, vehicleType, x, y, radius)

Zerstört alle Fahrzeuge und Schiffe im angegebenen Bereich ab.

#### Parameter

* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention")
* `x, y`: Koordinaten
* `radius [0-74]`: Radius

#### Beispiel

```lua
-- zerstört vom Spieler 1 alle Fahrzeuge und Schiffe an 320,170 im Radius von 15
SU.Vehicles.DeleteVehiclesInArea(1, -1, 320, 170, 15)
```
