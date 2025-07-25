---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetEntityType

## SU.Entity.GetEntityType(entityID)

Gibt den **generellen Typ** (Gebäude, Siedler, etc.) der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).



#### Welche Funktion genau brauche ich?

Ist die Entität mit der entityID:

* **generell** ein Gebäude, Siedler, Warenstapel, etc., **egal welches/r genau**\
  ⇒ [game.areplayerareasconnected-2.md](game.areplayerareasconnected-2.md "mention") ([game.areplayerareasconnected.md](game.areplayerareasconnected.md "mention"), [game.areplayerareasconnected-1.md](game.areplayerareasconnected-1.md "mention"))
* **grob gruppiert** ein Nahrungsgebäude, eine Mine, ein Soldat\
  ⇒ [game.areplayerareasconnected-9.md](game.areplayerareasconnected-9.md "mention")
* **spezifisch** eine Kaserne, ein Bogenschütze, ein Goldbarren, etc.\
  ⇒ [game.areplayerareasconnected-11.md](game.areplayerareasconnected-11.md "mention")



#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [ai-4.md](../../su-api-enums/ai-4.md "mention")

#### Beispiel

```lua
local entityType = SU.Entity.GetEntityType(entityID)
```
