---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.KillPlayerEntities

## SU.Game.KillPlayerEntities(playerID, killPlayer=0, deleteBuildingsMode=0, killEntitiesMode=0, deleteGoods=0)

Zerstört Entitäten vom angegebenen Spieler und setzt ihn auf ggf. auf "verloren".

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `killPlayer` (optional): 0 nichts, 1 setzt den Spieler auf "verloren"
* `deleteBuildingsMode` (optional): 0 nichts, 1 wie [buildings.crushbuilding.md](../../library-functions/buildings/buildings.crushbuilding.md "mention") (50% Rohstoffe), 2 wie [buildings.delete.md](../../library-functions/buildings/buildings.delete.md "mention")(keine Rohstoffe); Insassen und Arbeiter überleben
* `killEntitiesMode` (optional): 0 nichts, 1 auswählbare Einheiten sterben (ausgenommen Insassen (=Soldaten in Gebäuden)), 2 alle Einheiten
* `deleteGoods` (optional): 0 nichts, 1 löscht alle Waren im Land des Spielers; getragene und reservierte Waren werden nicht gelöscht

#### Beispiel

```lua
SU.Game.KillPlayerEntities(3, 0, 0, 0, 1)    -- alle freien Waren von Spieler 3 werden gelöscht
SU.Game.KillPlayerEntities(3, 0, 0, 1)    -- tötet alle freien auswählbaren Einheiten von Spieler 3
```
