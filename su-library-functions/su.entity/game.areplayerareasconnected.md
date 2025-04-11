---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetBaseType

## SU.Entity.GetBaseType(entityID)

Gibt die Basis-Klasse der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [ai-1.md](../../su-api-enums/ai-1.md "mention")

#### Beispiel

```lua
local baseType = SU.Entity.GetBaseType(entityID)
```
