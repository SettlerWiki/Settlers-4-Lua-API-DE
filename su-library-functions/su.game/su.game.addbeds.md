---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Game.AddBeds

## SU.Game.AddBeds(playerID, amount)

Fügt dem angegebenen Spieler die entsprechende Anzahl an Betten hinzu, die auch ohne Wohnhäuser bestehen bleiben.

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `amount`: Anzahl der hinzuzufügenden Betten

#### Beispiel

```lua
SU.Game.AddBeds(1, 100)    // fügt Spieler 1 100 Betten hinzu
```
