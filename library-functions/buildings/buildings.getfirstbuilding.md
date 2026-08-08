# Buildings.GetFirstBuilding

## `Buildings.GetFirstBuilding(Partei, Gebäudetyp)`

Gibt die erste (=**neueste**) Gebäude-ID vom angegebenen Gebäude-Typs zurück um beispielsweise durch alle Gebäude dieses Typs zu iterieren. ⇒ [su.buildings.getnextbuilding.md](../../su-library-functions/su.buildings/su.buildings.getnextbuilding.md "mention")

⇒ Siehe [su.buildings.getfirstbuilding.md](../../su-library-functions/su.buildings/su.buildings.getfirstbuilding.md "mention") um auch nach dem **Gebäudestatus** (Baustelle vs. fertiggestellt) zu filtern.

#### Notiz

* Partei ([game.numberofplayers.md](../game/game.numberofplayers.md "mention")) und Gebäudetyp ([#su-library](../../api-enums/buildings.md#su-library "mention")) müssen innerhalb des **gültigen Bereichs sein**, da ansonsten auf unbekannten Speicher zugegriffen wird, was zu undefinierten Verhalten und/oder Abstürzen führt!

#### Rückgabewert

* Einzigartige ID des gefundenen Gebäudes.
* 0: sonst / Fehler

#### Beispiel

```lua
local buildingID = Buildings.GetFirstBuilding(1, Buildings.GUARDTOWERSMALL)
```
