---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Settlers.GetSettlersInArea

## SU.Settlers.GetSettlersInArea(settlerIDs, playerID, settlerType, x, y, radius)

Gibt die Entity-Ids der Siedler im gegebenen Bereich zurück.

Ist eine auf Siedler limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `settlerIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local settlerIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention") , -1 wenn keine Siedler-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius [0-74]`: Radius des Bereichs

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Siedler.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local settlerIDs = {}    -- oder einmalig global definiert
local settlers, numSettlers = SU.Settlers.GetSettlersInArea(settlerIDs, playerID, settlerType, x, y, radius)

local settlerIDs = {}    -- oder einmalig global definiert
local numSettlers = SU.Settlers.GetSettlersInArea(settlerIDs, -1, -1, 115, 70, 10)
<strong>-- Alle Siedler bei 115/70 im Radius von 10
</strong>if numSettlers > 0 then
    dbg.stm(numSettlers) -- Anzahl der Siedler
    dbg.stm(settlerIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
