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

* 1\. `lua-table` (Entity-IDs): Eine Lua-Tabelle der gefundenen Siedler-IDs.
* 2\. `number` (Anzahl): Die Gesamtzahl der gefundenen Siedler.
* **WICHTIG**: In Lua müssen **ALLE Rückgabewerte** explizit **Variablen zugewiesen werden**. Wird nur ein Wert (oder gar keiner) entgegengenommen, führt dies **beim Verlassen** der Karte oft zum **Absturz des Spiels**. Dies gilt für alle Funktionen.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local settlers, numSettlers = SU.Settlers.GetSettlersInArea(playerId, settlerType, x, y, radius)

local settlers, numSettlers = SU.Settlers.GetSettlersInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Siedler bei 115/70 im Radius von 10
</strong>if numSettlers > 0 then
    dbg.stm(numSettlers) -- Anzahl der Siedler
    dbg.stm(settlers[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
