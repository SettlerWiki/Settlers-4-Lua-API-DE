---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetType

## SU.Entity.GetType(entityID)

Gibt den **spezifischen Typ** der angegebenen Entität zurück. Um den Typ richtig zu interpretieren, muss [su.entity.getentitytype.md](su.entity.getentitytype.md "mention") verwendet werden.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).



#### Welche Funktion genau brauche ich?

Ist die Entität mit der entityID:

* **generell** ein Gebäude, Siedler, Warenstapel, etc., **egal welches/r genau**\
  ⇒ [su.entity.getentitytype.md](su.entity.getentitytype.md "mention")
* **grob gruppiert** ein Nahrungsgebäude, eine Mine, ein Soldat\
  ⇒ [su.entity.getroleclass.md](su.entity.getroleclass.md "mention")
* **spezifisch** eine Kaserne, ein Bogenschütze, ein Goldbarren, etc.\
  ⇒ [su.entity.gettype.md](su.entity.gettype.md "mention")



#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [buildings.md](../../api-enums/buildings.md "mention")
* [goods.md](../../api-enums/goods.md "mention")
* [settlers.md](../../api-enums/settlers.md "mention")
* [vehicles.md](../../api-enums/vehicles.md "mention")
* [su.animals.md](../../su-api-enums/su.animals.md "mention")
* [su.objects.md](../../su-api-enums/su.objects.md "mention")
* [su.trees.md](../../su-api-enums/su.trees.md "mention")

#### Beispiel

```lua
local type = SU.Entity.GetType(entityID)
```
