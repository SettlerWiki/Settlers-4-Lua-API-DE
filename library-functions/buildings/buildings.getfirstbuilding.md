# Buildings.GetFirstBuilding

## `Buildings.GetFirstBuilding(Partei, Gebäudetyp)`

Sucht nach dem Gebäude der angegebenen Partei und des angegebenen Gebäudetyps und gibt das neueste Gebäude zurück.

#### Notiz

* Partei ([game.numberofplayers.md](../game/game.numberofplayers.md "mention")) und Gebäudetyp ([#su-library](../../api-enums/buildings.md#su-library "mention")) müssen innerhalb des **gültigen Bereichs sein**, da ansonsten auf unbekannten Speicher zugegriffen wird, was zu undefinierten Verhalten und/oder Abstürzen führt!

#### Rückgabewert

* Einzigartige ID des gefundenen Gebäudes.
* 0: sonst / Fehler

#### Beispiel

```lua
local buildingID = Buildings.GetFirstBuilding(1, Buildings.GUARDTOWERSMALL)
```
