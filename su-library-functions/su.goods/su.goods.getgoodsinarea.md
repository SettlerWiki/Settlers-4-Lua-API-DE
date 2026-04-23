---
description: 'SU Library: ab Version 0.6.4'
---

# SU.Goods.GetGoodsInArea

## SU.Goods.GetGoodsInArea(playerId, goodType, x, y, radius)

Gibt die Entity-Ids der Waren im gegebenen Bereich zurück.

Ist eine auf Waren limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `goodType`: [goods.md](../../api-enums/goods.md "mention") , -1 wenn keine Waren-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* 1\. `lua-table` (Entity-IDs): Eine Lua-Tabelle der gefundenen Waren-IDs.
* 2\. `number` (Anzahl): Die Gesamtzahl der gefundenen Waren.
* **WICHTIG**: In Lua müssen **ALLE Rückgabewerte** explizit **Variablen zugewiesen werden**. Wird nur ein Wert (oder gar keiner) entgegengenommen, führt dies **beim Verlassen** der Karte oft zum **Absturz des Spiels**. Dies gilt für alle Funktionen.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local goods, numGoods = SU.Entity.GetGoodsInArea(playerId, goodType, x, y, radius)

local goods, numGoods = SU.Entity.GetGoodsInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Waren bei 115/70 im Radius von 10
</strong>if numGoods > 0 then
    dbg.stm(numGoods) -- Anzahl der Waren
    dbg.stm(entities[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
