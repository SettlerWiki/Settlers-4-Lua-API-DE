---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Entity.GetEntitiesInArea

## SU.Entity.GetEntitiesInArea(entityIDs, playerID, entityType, x, y, radius, skipInhabitants=1)

Gibt die Entity-IDs der Entitäten im gegebenen Bereich zurück.

**Achtung**: Dies liefert beispielsweise bei Gebäuden die IDs von: Gebäude, Arbeiter, Insassen (je nach Einstellung) und die Warenstapel vom Gebäude - falls in Reichweite.

**Andere limitierte Versionen** sind:

* [su.buildings.getbuildingsinarea.md](../su.buildings/su.buildings.getbuildingsinarea.md "mention")
* [su.goods.getgoodsinarea.md](../su.goods/su.goods.getgoodsinarea.md "mention")
* [su.settlers.getsettlersinarea.md](../su.settlers/su.settlers.getsettlersinarea.md "mention")
* [su.vehicles.getvehiclesinarea.md](../su.vehicles/su.vehicles.getvehiclesinarea.md "mention")

#### Parameter

* `entityIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local entityIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `entityType`: [su.entitytypes.md](../../su-api-enums/su.entitytypes.md "mention") , -1 wenn keine Entity-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs
* `skipInhabitants` (optional): ob Insassen (Soldaten) beachtet werden sollen oder nicht. Arbeiter werden immer berücksichtigt!

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Entitäten.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Entity.GetEntitiesInArea(entityIDs, playerID, entityType, x, y, radius)

local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Entity.GetEntitiesInArea(entityIDs, -1, -1, 115, 70, 10)
<strong>-- Alle Entitäten bei 115/70 im Radius von 10
</strong>if numEntities > 0 then
    dbg.stm(numEntities) -- Anzahl der Entitäten
    dbg.stm(entityIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
