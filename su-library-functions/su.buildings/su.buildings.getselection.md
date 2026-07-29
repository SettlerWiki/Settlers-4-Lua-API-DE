---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetSelection

## SU.Buildings.GetSelection()

Gibt die Entity-ID des aktuell ausgewählten Gebäudes zurück (sowohl von fertigen als auch von Baustellen).\
⇒ ist eine auf Gebäude limitierte Version von [su.entity.getselection.md](../su.entity/su.entity.getselection.md "mention").

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [lokale-vs-netzwerk-funktionen.md](../../tutorials/advanced-tipps/lokale-vs-netzwerk-funktionen.md "mention")).

#### Rückgabewerte

* `buildingID`: ID des ausgewählten Gebäudes
* 0 sonst / Fehler

#### Beispiel

```lua
local selectedBuildingID = SU.Buildings.GetSelection()
```
