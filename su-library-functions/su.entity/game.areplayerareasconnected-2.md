---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetEntityType

## SU.Entity.GetEntityType(entityID)

Gibt die den Typ (Gebäude, Siedler, etc.) der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [ai-3.md](../../su-api-enums/ai-3.md "mention")

#### Beispiel

```lua
local entityType = SU.Entity.GetEntityType(entityID)
```
