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

* LUA-Table von Entity-Ids der Waren im Bereich

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local goods = SU.Entity.GetGoodsInArea(playerId, goodType, x, y, radius)

local goods = SU.Entity.GetGoodsInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Waren bei 115/70 im Radius von 10
</strong>if type(goods) == "table" then
    local numGoods = getn(goods)
    dbg.stm(numGoods) -- Anzahl der Waren
    if numGoods > 0 then
    	dbg.stm(entities[1]) -- Erster Eintrag der Id Liste
    end
end
</code></pre>
