---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Vehicles.GetVehiclesInArea

## SU.Vehicles.GetVehiclesInArea(vehicleIDs, playerID, vehicleType, x, y, radius)

Gibt die Entity-IDs der Fahrzeuge/Schiffe im gegebenen Bereich zurück.

Ist eine auf Fahrzeuge/Schiffe limitierte Version von [su.entity.getentitiesinarea.md](../su.entity/su.entity.getentitiesinarea.md "mention").

#### Parameter

* `vehicleIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local vehicleIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention") , -1 wenn keine Fahrzeug-/Schiff-Typen gefiltert werden sollen
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius [0-74]`: Radius des Bereichs

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Fahrzeuge/Schiffe.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local vehicleIDs = {}    -- oder einmalig global definiert
local numVehicles = SU.Vehicles.GetVehiclesInArea(vehicleIDs, playerID, vehicleType, x, y, radius)

local vehicleIDs = {}    -- oder einmalig global definiert
local numVehicles = SU.Vehicles.GetVehiclesInArea(vehicleIDs, -1, -1, 115, 70, 10)
<strong>-- Alle Fahrzeuge/Schiffe bei 115/70 im Radius von 10
</strong>if numVehicles > 0 then
    dbg.stm(numVehicles) -- Anzahl der Fahrzeuge/Schiffe
   	dbg.stm(vehicleIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
