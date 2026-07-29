---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.GetNumberOfTeams

## SU.Game.GetNumberOfTeams()

Gibt die Anzahl an Teams zurück.

**Achtung: funktioniert NICHT in "new\_game"!**\
⇒ stattdessen **"**&#x45;vents.FIRST\_TICK\_OF\_NEW\_GAME" o.ä. (siehe [request\_event](https://app.gitbook.com/s/auUjVOZHHg4G6b8lVuXs/library-functions/global-functions/request_event "mention"))

#### Rückgabewert

* Anzahl an Teams

#### Beispiel

```lua
local numTeams = SU.Game.GetNumberOfTeams()
```
