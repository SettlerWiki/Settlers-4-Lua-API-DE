---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Vehicles.GetSelection

## SU.Vehicles.GetSelection(vehicleIDs)

Gibt die Fahrzeug- und Schiff-IDs der aktuell ausgewählten Entitäten zurück.\
⇒ ist eine auf Fahrzeuge/Schiffe limitierte Version von [su.entity.getselection.md](../su.entity/su.entity.getselection.md "mention").

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [lokale-vs-netzwerk-funktionen.md](../../tutorials/advanced-tipps/lokale-vs-netzwerk-funktionen.md "mention")).

#### Parameter

* `vehicleIDs`: **Ziel-Tabelle**: Eine vor dem Funktionsaufruf erstellte Tabelle (z. B. `local vehicleIDs = {}`, siehe Beispiel unten), die dann von dieser Funktion mit den gefundenen Entity-IDs befüllt wird. **Achtung**: Bereits enthaltene Daten in dieser Tabelle werden dabei überschrieben!

#### Rückgabewert

* `number` (Anzahl): Die Gesamtzahl der gefundenen Entitäten.
* **Hinweis**_:_ Die eigentlichen Entity-IDs werden nicht als Rückgabewert geliefert, sondern direkt in die als ersten Parameter übergebene Ziel-Tabelle geschrieben.

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Vehicles.GetSelection(entityIDs)

local entityIDs = {}    -- oder einmalig global definiert
local numEntities = SU.Vehicles.GetSelection(entityIDs)
<strong>-- Alle Entitäten bei 115/70 im Radius von 10
</strong>if numEntities > 0 then
    dbg.stm(numEntities) -- Anzahl der Entitäten
    dbg.stm(entityIDs[1]) -- Erster Eintrag der Id Liste
end
</code></pre>
