---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetOwner

## SU.Entity.GetOwner(entityID)

Gibt den Besitzer (Spieler-ID) der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Notiz

* Macht natürlich **nur Sinn für Entitäten mit Besitzer**...

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* Besitzer / Spieler-ID
* 0: sonst / Fehler

#### Beispiel

```lua
local owner = SU.Entity.GetOwner(entityID)
```
