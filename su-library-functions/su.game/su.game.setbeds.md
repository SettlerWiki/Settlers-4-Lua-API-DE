---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Game.SetBeds

## SU.Game.SetBeds(playerID, amount)

Setzt vom angegebenen Spieler die Anzahl der Betten, **die auch ohne Wohnhäuser bestehen bleiben. Betten von Wohnhäusern bleiben weiterhin zusätzlich bestehen.**

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `amount`: Anzahl der Betten

#### Beispiel

```lua
SU.Game.SetBeds(1, 100)    // Spieler 1 hat nun 100 Betten (+ die von Wohnhäusern)
```
