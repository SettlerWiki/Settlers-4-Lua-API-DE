---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.GetStartingPosition

## SU.Game.GetStartingPosition(playerID)

Gibt die Start-Position zurück.

**Achtung: funktioniert NICHT in "new\_game"!**\
⇒ stattdessen **"**&#x45;vents.FIRST\_TICK\_OF\_NEW\_GAME" o.ä. (siehe [request\_event](https://app.gitbook.com/s/auUjVOZHHg4G6b8lVuXs/library-functions/global-functions/request_event "mention"))

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**

#### Rückgabewert

* `x, y`: Start-Position
* `0,0` oder `-1,-1`: sonst / Fehler

#### Beispiel

```lua
local x, y = SU.Game.GetStartingPosition(3)    -- Start-Position von Spieler 3
```
