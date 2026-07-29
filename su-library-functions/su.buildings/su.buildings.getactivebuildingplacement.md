---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetActiveBuildingPlacement

## SU.Buildings.GetActiveBuildingPlacement()

Gibt den Gebäude-Typ des aktuell im Menü ausgewählten Gebäudes zurück, während es auf der Karte platziert werden kann.

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [lokale-vs-netzwerk-funktionen.md](../../tutorials/advanced-tipps/lokale-vs-netzwerk-funktionen.md "mention")).

#### Rückgabewert

* Gebäude-Typ [buildings.md](../../api-enums/buildings.md "mention")
* 0: sonst (nicht aktiv) / Fehler

#### Beispiel

```lua
local buildingType = SU.Buildings.GetActiveBuildingPlacement()
```
