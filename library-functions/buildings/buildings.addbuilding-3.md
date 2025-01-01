---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Buildings.AddConstructionSite

## `Buildings.AddConstructionSite(x, y, Spieler, Gebäude)`

Platziert eine Baustelle des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem Radius von 4 Feldern nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

⇒ Radius: siehe [buildings.addbuilding-4.md](buildings.addbuilding-4.md "mention")

#### Rückgabewert

Eindeutige Gebäude-ID oder 0, wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID = Buildings.AddConstructionSite(100,100, 1, Buildings.GUARDTOWERSMALL)
```
