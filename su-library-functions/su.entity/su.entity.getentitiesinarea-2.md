---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Entity.GetSelection

## SU.Entity.GetSelection(entityIDs, entityType=-1)

Gibt die Entity-IDs der aktuell ausgewählten Entitäten zurück.

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [place-buildings-1.md](../../tutorials/advanced-tipps/place-buildings-1.md "mention")).

**Andere limitierte Versionen** sind:

* [su.buildings.getbuildingsinarea-1.md](../su.buildings/su.buildings.getbuildingsinarea-1.md "mention")
* [su.entity.getentitiesinarea.md](../su.game/su.entity.getentitiesinarea.md "mention")
* [su.entity.getentitiesinarea.md](../su.settlers/su.entity.getentitiesinarea.md "mention")
* [su.entity.getentitiesinarea.md](../su.vehicles/su.entity.getentitiesinarea.md "mention")

#### Parameter

* `entityIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local entityIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!
* `entityType`: [su.entitytypes.md](../../su-api-enums/su.entitytypes.md "mention") , -1 wenn keine Entity-Typen gefiltert werden sollen

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Entitäten.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Entity.GetSelection(entityIDs, entityType)

local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Entity.GetSelection(entityIDs, -1)
<strong>-- Alle Entitäten bei 115/70 im Radius von 10
</strong>if numEntities > 0 then
    dbg.stm(numEntities) -- Anzahl der Entitäten
    dbg.stm(entityIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
