---
description: 'SU Library: ab Version 0.6.0'
---

# SU.Buildings.GetFirstBuildingInArea

## SU.Buildings.GetFirstBuildingInArea(playerId, buildingType, x, y, radius)

Gibt die Entity-Id des ersten gefundenen Gebäudes im gegebenen Bereich zurück.

#### Parameter

* `playerId`: ID des Spielers (1-8), -1 wenn keine Spieler gefiltert werden sollen
* `buildingType`: ID des Gebäude-Typs (siehe [Enum-Tabelle](../../api-enums/buildings.md)), -1 wenn keine Gebäude-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* Entity-Id vom Gebäude
* 0: wenn kein Gebäude gefunden wurde

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local buildingId = SU.Buildings.GetFirstBuildingInArea(playerId, buildingType, x, y, radius)
<strong>
</strong><strong>local buildings = SU.Buildings.GetFirstBuildingInArea(-1, -1, 115, 70, 10)
</strong><strong>-- Irgendein Gebäude bei 115/70 im Radius von 10
</strong>	if buildingId > 0 then
		dbg.stm(buildingId) -- Entity-Id des Gebäudes, wenn gefunden
	endl
end
</code></pre>
