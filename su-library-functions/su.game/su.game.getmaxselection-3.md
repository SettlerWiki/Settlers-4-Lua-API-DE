---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.GetPlayersOfTeam

## SU.Game.GetPlayersOfTeam(playerIDs, teamID)

Gibt die Anzahl an Teams zurück.

**Achtung: funktioniert NICHT in "new\_game"!**\
⇒ stattdessen **"**&#x45;vents.FIRST\_TICK\_OF\_NEW\_GAME" o.ä. (siehe [request\_event](https://app.gitbook.com/s/auUjVOZHHg4G6b8lVuXs/library-functions/global-functions/request_event "mention"))

#### Parameter

* `playerIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local playerIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `teamID`: ID des Teams

#### Rückgabewert

* `number` (Anzahl): Anzahl der Spieler im angegebenen Team
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

```lua
local playerIDs = {}
local numPlayers = SU.Game.GetPlayersOfTeam(playerIDs, 2)    -- liefert Spieler-IDs vom Team 2
```
