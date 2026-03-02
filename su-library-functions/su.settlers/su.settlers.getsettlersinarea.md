---
description: 'SU Library: ab Version 0.6.4'
---

# SU.Settlers.GetSettlersInArea

## SU.Settlers.GetSettlersInArea(playerId, settlerType, x, y, radius)

Gibt die Entity-Ids der Siedler im gegebenen Bereich zurück.

Ist eine auf Siedler limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention") , -1 wenn keine Siedler-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* LUA-Table von Entity-Ids der Siedler im Bereich

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local settlers = SU.Settlers.GetSettlersInArea(playerId, settlerType, x, y, radius)

local settlers = SU.Settlers.GetSettlersInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Siedler bei 115/70 im Radius von 10
</strong>if type(settlers) == "table" then
    local numSettlers = getn(settlers)
    dbg.stm(numSettlers) -- Anzahl der Siedler
    if numSettlers > 0 then
    	dbg.stm(settlers[1]) -- Erster Eintrag der Id Liste
    end
end
</code></pre>
