---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.GetBuildingInfo

## SU.GameData.GetBuildingInfo(tribe, buildingType, buildingField)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Liest einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Gebäudes aus den aktuell im Spiel verwendeten Spieldaten aus.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `buildingField`: [#building-fields](../../su-api-enums/su.gamedata.md#building-fields "mention")

#### Rückgabewert

* `number` – Der ausgelesene Wert des Gebäudefeldes

#### Beispiel

```lua
-- liest die Gold-Kosten für das 4. Zierobjekt der Wikinger aus
local goldCosts = SU.GameData.GetBuildingInfo(SU.Tribes.VIKING, Buildings.EYECATCHER04, SU.GameData.BUILDING_FIELD_GOLD)
```
