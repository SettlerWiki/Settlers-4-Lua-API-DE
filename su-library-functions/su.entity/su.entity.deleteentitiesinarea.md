---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Entity.DeleteEntitiesInArea

## SU.Entity.DeleteEntitiesInArea(playerID, entityType, x, y, radius, killInhabitantsAndWorker=0)

Löscht/Zerstört die angegebene Entität (**beschränkt** auf: Gebäude, Siedler, Schiffe und Fahrzeuge) mit Sterbeanimation. Bei Gebäuden werden **keine Rohstoffe zurückerstattet**.\
⇒ Um Deko-/Objekte zu löschen: [map.deletedecoobject.md](../../library-functions/map/map.deletedecoobject.md "mention")

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

**Andere limitierte Versionen** sind:

* [su.buildings.deletebuildingsinarea.md](../su.buildings/su.buildings.deletebuildingsinarea.md "mention")
* [su.goods.deletegoodsinarea.md](../su.goods/su.goods.deletegoodsinarea.md "mention")
* [su.settlers.deletesettlersinarea.md](../su.settlers/su.settlers.deletesettlersinarea.md "mention")
* [su.vehicles.deletevehiclesinarea.md](../su.vehicles/su.vehicles.deletevehiclesinarea.md "mention")

#### Notiz

* Waren, die aktuell getragen werden, werden nicht von dieser Funktion erkannt. Erst muss der tragende Siedler sterben, der die Ware damit fallen lässt, dann kann die Ware gelöscht werden.

#### Parameter

* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `entityType`: [su.entitytypes.md](../../su-api-enums/su.entitytypes.md "mention") , -1 wenn keine Entity-Typen gefiltert werden sollen
* `x, y`: Koordinaten
* `radius [0-74]`: Radius des Bereichs
* `killInhabitantsAndWorker`(optional): ob Insassen (Soldaten) und Arbeiter direkt mit dem Gebäude gelöscht werden sollen (1) oder nicht (0)

#### Beispiel

```lua
-- löscht alle Entities vom Spieler 1 im Bereich, inkl. Insassen und Arbeiter
SU.Entity.DeleteEntitiesInArea(1, -1, 130, 205, 10, 1)
```
