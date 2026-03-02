---
description: 'SU Library: ab Version 0.6.4'
---

# SU.Vehicles.GetVehiclesInArea

## SU.Vehicles.GetVehiclesInArea(playerId, vehicleType, x, y, radius)

Gibt die Entity-Ids der Fahrzeuge/Schiffe im gegebenen Bereich zurück.

Ist eine auf Fahrzeuge/Schiffe limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention") , -1 wenn keine Fahrzeug-/Schiff-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs

#### Rückgabewert

* LUA-Table von Entity-Ids der Fahrzeuge/Schiffe im Bereich

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local vehicles = SU.Vehicles.GetVehiclesInArea(playerId, vehicleType, x, y, radius)

local vehicles = SU.Vehicles.GetVehiclesInArea(-1, -1, 115, 70, 10)
<strong>-- Alle Siedler bei 115/70 im Radius von 10
</strong>if type(vehicles) == "table" then
    local numVehicles = getn(vehicles)
    dbg.stm(numVehicles) -- Anzahl der Fahrzeuge/Schiffe
    if numVehicles > 0 then
    	dbg.stm(vehicles[1]) -- Erster Eintrag der Id Liste
    end
end
</code></pre>
