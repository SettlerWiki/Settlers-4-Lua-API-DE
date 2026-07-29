---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Goods.GetGoodsInArea

## SU.Goods.GetGoodsInArea(goodIDs, playerID, goodType, x, y, radius)

Gibt die Entity-IDs der Waren im gegebenen Bereich zurück.

Ist eine auf Waren limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `goodIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local goodIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `goodType`: [goods.md](../../api-enums/goods.md "mention") , -1 wenn keine Waren-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius [0-74]`: Radius des Bereichs

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Waren.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local goodIDs = {}    -- oder einmalig global definiert
local numGoods = SU.Entity.GetGoodsInArea(goodIDs, playerID, goodType, x, y, radius)

local goodIDs = {}    -- oder einmalig global definiert
local numGoods = SU.Entity.GetGoodsInArea(goodIDs, -1, -1, 115, 70, 10)
<strong>-- Alle Waren bei 115/70 im Radius von 10
</strong>if numGoods > 0 then
    dbg.stm(numGoods) -- Anzahl der Waren
    dbg.stm(goodIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
