---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetRoleClass

## SU.Entity.GetRoleClass(entityID)

Gibt **grob gruppiert** die Klassen-Rolle der angegebenen Entität zurück.

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

* [su.roleclasses.md](../../su-api-enums/su.roleclasses.md "mention")

#### Beispiel

```lua
local roleClass = SU.Entity.GetRoleClass(entityID)
```
