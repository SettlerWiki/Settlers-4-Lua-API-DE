---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetSelection

## SU.Buildings.GetSelection()

Gibt die Entity-ID des aktuell ausgewählten Gebäudes zurück (sowohl von fertigen als auch von Baustellen).

#### Rückgabewerte

* `buildingID`: ID des ausgewählten Gebäudes
* 0 sonst / Fehler

#### Beispiel

```lua
local selectedBuildingID = SU.Buildings.GetSelection()
```
