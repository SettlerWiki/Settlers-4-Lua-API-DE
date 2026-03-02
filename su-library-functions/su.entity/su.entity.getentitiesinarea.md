---
description: 'SU Library: ab Version 0.6.4'
---

# SU.Entity.GetEntitiesInArea

## SU.Entity.GetEntitiesInArea(playerId, entityType, x, y, radius)

Gibt die Entity-Ids der Entitäten im gegebenen Bereich zurück.

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `entityType`: [su.entitytypes.md](../../su-api-enums/su.entitytypes.md "mention") , -1 wenn keine Entity-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* LUA-Table von Entity-Ids der Entitäten im Bereich

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local entities = SU.Entity.GetEntitiesInArea(playerId, entityType, x, y, radius)

local entities = SU.Entity.GetEntitiesInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Entitäten bei 115/70 im Radius von 10
</strong>if type(entities) == "table" then
    local numEntities = getn(entities)
    dbg.stm(numEntities) -- Anzahl der Entitäten
    if numEntities > 0 then
    	dbg.stm(entities[1]) -- Erster Eintrag der Id Liste
    end
end
</code></pre>
