# Buildings.ExistsBuildingInArea

## `Buildings.ExistsBuildingInArea(Partei, Gebäudetyp, x, y, Radius, Gebäudestatus)`

Testet, ob um die Koordinaten `x, y` im `Radius` ein Gebäude des `Gebäudetyp` der `Partei` vorhanden ist.

`Radius`: > 0

`Gabäudestatus` scheint keinen Einfluss zu haben...

#### Rückgabewert

0: existiert **nicht**\
1: Gebäude existiert

#### Beispiel

```lua
Buildings.ExistsBuildingInArea(2,Buildings.GUARDTOWERBIG,468,323,1, Buildings.READY)
Buildings.ExistsBuildingInArea(2,Buildings.GUARDTOWERBIG,468,323,1, Buildings.UNDERCONST
```
