# Buildings.GetFirstBuilding

## `Buildings.GetFirstBuilding(Partei, Gebäudetyp)`

Sucht nach dem Gebäude der angegebenen Partei und des angegebenen Gebäudetyps und gibt das neueste Gebäude zurück.

#### Rückgabewert

Einzigartige ID des gefundenen Gebäudes.

#### Beispiel

```lua
local buildingID = Buildings.GetFirstBuilding(1, Buildings.GUARDTOWERSMALL)
```
