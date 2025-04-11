---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetRoleClass

## SU.Entity.GetRoleClass(entityID)

Gibt die Klassen-Rolle der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [ai-8.md](../../su-api-enums/ai-8.md "mention")

#### Beispiel

```lua
local roleClass = SU.Entity.GetRoleClass(entityID)
```
