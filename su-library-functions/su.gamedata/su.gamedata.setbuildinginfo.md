---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.SetBuildingInfo

## SU.GameData.SetBuildingInfo(tribe, buildingType, buildingField, value)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Setzt/überschreibt einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Gebäudes aus den aktuell im Spiel verwendeten Spieldaten.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `buildingField`: [#building-fields](../../su-api-enums/su.gamedata.md#building-fields "mention")
* `value`: neuer Wert, der zugewiesen wird

#### Rückgabewert

* 1: erfolgreich
* -1: sonst / Fehler

#### Beispiel

```lua
-- setzt die Gold-Kosten für das NEU gebaute 4. Zierobjekt der Wikinger auf 8
local success = SU.GameData.SetBuildingInfo(SU.Tribes.VIKING, Buildings.EYECATCHER04, SU.GameData.BUILDING_FIELD_GOLD, 8)
```
