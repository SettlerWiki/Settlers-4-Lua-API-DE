---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetBuildingsInArea

## SU.Buildings.GetBuildingsInArea(buildingIDs, playerID, buildingType, x, y, radius, buildingState=Buildings.ALL)

Gibt die Entity-IDs der Gebäude (sowohl fertige als auch Baustellen) im gegebenen Bereich zurück.

Ist eine auf Gebäude limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `buildingIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local buildingIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `buildingType`: ID des Gebäude-Typs (siehe [Enum-Tabelle](../../api-enums/buildings.md)), -1 wenn keine Gebäude-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs
* `buildingState` (optional): Gebäudestatus nach dem gesucht werden soll (siehe [buildings.md](../../api-enums/buildings.md "mention"))

#### Rückgabewerte

* `number` (Anzahl): Die Gesamtzahl der gefundenen Gebäude.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local buildingIDs = {}    -- oder einmalig global definiert
local numBuildings = SU.Buildings.GetBuildingsInArea(buildingIDs, playerId, buildingType, x, y, radius)

local buildingIDs = {}    -- oder einmalig global definiert
local numBuildings = SU.Buildings.GetBuildingsInArea(buildingIDs, -1, -1, 115, 70, 10)
<strong>-- Alle Gebäude bei 115/70 im Radius von 10
</strong>if numBuildings > 0 then
    dbg.stm(numBuildings) -- Anzahl der Gebäude
    dbg.stm(buildingIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
