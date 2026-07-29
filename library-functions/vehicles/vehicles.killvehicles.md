# Vehicles.KillVehicles

## `Vehicles.KillVehicles(Spieler, Fahrzeugtyp, x, y, Radius)`

Entfernt alles Fahrzeuge eines bestimmten Spielers und eines bestimmten Typs aus einem bestimmten Bereich.

`Radius [0-74]`

#### Rückgabewert

True oder False

#### Beispiel

```lua
Vehicles.KillVehicles(2, Vehicles.FERRY, 195, 268, 10)
Vehicles.KillVehicles(2, Vehicles.WARSHIP, 153, 228, 10)
```
