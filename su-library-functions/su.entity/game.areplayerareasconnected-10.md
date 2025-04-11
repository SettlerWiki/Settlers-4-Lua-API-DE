---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetTribe

## SU.Entity.GetTribe(entityID)

Gibt das Volk des Besitzers der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* [ai-11.md](../../su-api-enums/ai-11.md "mention")

#### Beispiel

```lua
local tribe = SU.Entity.GetTribe(entityID)
```
