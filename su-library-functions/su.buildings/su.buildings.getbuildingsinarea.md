---
description: 'SU Library: ab Version 0.6.0'
---

# SU.Buildings.GetBuildingsInArea

## SU.Buildings.GetBuildingsInArea(playerId, buildingType, x, y, radius)

Gibt die Entity-Ids der Gebäude im gegebenen Bereich zurück.

Ist eine auf Gebäude limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `buildingType`: ID des Gebäude-Typs (siehe [Enum-Tabelle](../../api-enums/buildings.md)), -1 wenn keine Gebäude-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewerte

* 1\. `lua-table` (Entity-IDs): Eine Lua-Tabelle der gefundenen Gebäude-IDs.
* 2\. `number` (Anzahl): Die Gesamtzahl der gefundenen Gebäude.
* **WICHTIG**: In Lua müssen **ALLE Rückgabewerte** explizit **Variablen zugewiesen werden**. Wird nur ein Wert (oder gar keiner) entgegengenommen, führt dies **beim Verlassen** der Karte oft zum **Absturz des Spiels**. Dies gilt für alle Funktionen.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local buildings, numBuildings = SU.Buildings.GetBuildingsInArea(playerId, buildingType, x, y, radius)

local buildings, numBuildings = SU.Buildings.GetBuildingsInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Gebäude bei 115/70 im Radius von 10
</strong>if numBuildings > 0 then
    dbg.stm(numBuildings) -- Anzahl der Gebäude
    dbg.stm(buildings[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
