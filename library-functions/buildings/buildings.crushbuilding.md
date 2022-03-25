# Buildings.CrushBuilding

## `Buildings.CrushBuilding(ID)`

Reißt ein Gebäude ab. Dies kann unter anderem genutzt werden, um den Spieler am Bau bestimmter Gebäude zu hindern.

#### Rückgabewert

none

#### Beispiel

```lua
Buildings.CrushBuilding(Buildings.GetFirstBuilding(4, Buildings.GUARDTOWERSMALL))  --//Ermittelt den kleinen Turm des vierten Spielers mit der kleinsten ID und reißt ihn ab.
Buildings.CrushBuilding(Buildings.AddBuilding(150,75,1,Buildings.GUARDTOWERBIG)) --//P
```
