---
description: 'SU Library: erst ab Version 0.6.2 verfügbar!'
---

# SU.Map.TakeMap

## SU.Map.TakeMap(\[playerID=localPlayerID\[, forced=1]])

Spieler `playerID` nimmt die gesamte Karte ein, standardmäßig werden andere Spieler getötet und ihnen das Land weggenommen.

#### Notiz

* Diese Funktion ist im Hintergrund sehr aufwändig und führt oftmals zu FEs, z.B. häufig, wenn gleichzeitig Einheiten ausgewählt sind.

#### Parameter

* `playerID [1-8]` (optional): Spieler-ID, **Index 0 ist ungültig!**
* `forced [0,1]` (optional): 0 nimmt nur freies Land ein, 1 nimmt anderen Spielern das Land weg (und tötet sie dadurch)

#### Beispiel

```lua
SU.Map.TakeMap()    -- du nimmst die gesamte Karte ein, andere Spieler sterben
SU.Map.TakeMap(3, 0)    -- Spieler 3 nimmt alles freie Land ein
```
