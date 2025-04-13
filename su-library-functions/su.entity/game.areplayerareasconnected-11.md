---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetType

## SU.Entity.GetType(entityID)

Gibt den **spezifischen Typ** der angegebenen Entität zurück. Um den Typ richtig zu interpretieren, muss [game.areplayerareasconnected-2.md](game.areplayerareasconnected-2.md "mention") verwendet werden.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).



#### Welche Funktion genau brauche ich?

Ist die Entität mit der entityID:

* **generell** ein Gebäude, Siedler, Warenstapel, etc., **egal welches/r genau**\
  ⇒ [game.areplayerareasconnected-2.md](game.areplayerareasconnected-2.md "mention")
* **grob gruppiert** ein Nahrungsgebäude, eine Mine, ein Soldat\
  ⇒ [game.areplayerareasconnected-9.md](game.areplayerareasconnected-9.md "mention")
* **spezifisch** eine Kaserne, ein Bogenschütze, ein Goldbarren, etc.\
  ⇒ [game.areplayerareasconnected-11.md](game.areplayerareasconnected-11.md "mention")



#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [buildings.md](../../api-enums/buildings.md "mention")
* [goods.md](../../api-enums/goods.md "mention")
* [settlers.md](../../api-enums/settlers.md "mention")
* [vehicles.md](../../api-enums/vehicles.md "mention")
* [ai.md](../../su-api-enums/ai.md "mention")
* [ai-6.md](../../su-api-enums/ai-6.md "mention")
* [ai-9.md](../../su-api-enums/ai-9.md "mention")

#### Beispiel

```lua
local type = SU.Entity.GetType(entityID)
```
