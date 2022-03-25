# Buildings.ExistsBuildingInArea

## `Buildings.ExistsBuildingInArea(Partei, Gebäudetyp, x, y, radius, Gebäudestatus)`

Ähnlich wie Buildings.Amount, aber auf einen bestimmten Bereich begrenzt.

#### Rückgabewert

Anzahl der gefundenen Gebäude.

#### Beispiel

```lua
Buildings.ExistsBuildingInArea(2,Buildings.GUARDTOWERBIG,468,323,1, Buildings.READY)
Buildings.ExistsBuildingInArea(2,Buildings.GUARDTOWERBIG,468,323,1, Buildings.UNDERCONST
```
