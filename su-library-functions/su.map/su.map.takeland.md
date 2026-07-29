---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Map.TakeLand

## SU.Map.TakeLand(playerID, x, y, radius=0, takeLandMode=0, destroyBuildingsMode=0, killInhabitantsAndWorker=0)

Nimmt Land für den angegebenen Spieler ein. Je nach Optionen nur freies oder auch bereits besetztes Land.

#### Parameter

* `playerID [1-8]` (optional): Spieler-ID, **Index 0 ist ungültig!**
* `x,y`: Koordinaten
* `radius [0-74]` (optional): Radius
* `takeLandMode` (optional): 0 nur freies, 1 auch besetztes aber ungeschütztes (kein Turm in der Nähe), 2 jedes Land
* `destroyBuildingsMode` (optional): 0 nichts, 1 wie [buildings.crushbuilding.md](../../library-functions/buildings/buildings.crushbuilding.md "mention")(50% Rohstoffe erstattet), 2 wie [buildings.delete.md](../../library-functions/buildings/buildings.delete.md "mention") (keine Rohstoffe erstattet)
* `killInhabitantsAndWorker` (optional): 0 nichts, 1 tötet Insassen (=Soldaten) und Arbeiter (auch außerhalb des Gebäudes)

#### Beispiel

```lua
-- Spieler 2 bekommt das Land an (40,50) im Radius 25, aber nur ungeschütztes
SU.Map.TakeLand(2, 40, 50, 25, 1)
```
