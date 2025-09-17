---
description: 'SU Library: ab Version 0.6.0'
---

# SU.Buildings.GetBuildingsInArea

## SU.Buildings.GetBuildingsInArea(playerId, buildingType, x, y, radius)

Gibt die Entity-Ids der Gebäude im gegebenen Bereich zurück.

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `buildingType`: ID des Gebäude-Typs (siehe [Enum-Tabelle](../../api-enums/buildings.md)), -1 wenn keine Gebäude-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* LUA-Table von Entity-Ids der Gebäude im Bereich

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local buildings = SU.Buildings.GetBuildingsInArea(playerId, buildingType, x, y, radius)

local buildings = SU.Buildings.GetBuildingsInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Gebäude bei 115/70 im Radius von 10
</strong>    if type(buildings) == "table" then
    	dbg.stm(getn(buildings)) -- Anzahl der Gebäude
    	dbg.stm(buildings[1]) -- Erster Eintrag der Id Liste
    end
end
</code></pre>
