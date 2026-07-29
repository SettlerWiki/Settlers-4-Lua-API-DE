---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.GetTeamOfPlayer

## SU.Game.GetTeamOfPlayer(playerID)

Gibt die Team-ID zurück.

**Achtung: funktioniert NICHT in "new\_game"!**\
⇒ stattdessen **"**&#x45;vents.FIRST\_TICK\_OF\_NEW\_GAME" o.ä. (siehe [request\_event](https://app.gitbook.com/s/auUjVOZHHg4G6b8lVuXs/library-functions/global-functions/request_event "mention"))

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**

#### Rückgabewert

* Team-ID
* 0 sonst / Fehler

#### Beispiel

```lua
local teamID = SU.Game.GetTeamOfPlayer(3)    -- liefert das Team von Spieler 3
```
