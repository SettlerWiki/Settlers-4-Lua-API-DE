---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.GetSettlerInfo

## SU.GameData.GetSettlerInfo(tribe, settlerType, settlerField)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Liest einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Siedlers aus den aktuell im Spiel verwendeten Spieldaten aus.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `settlerField`: [#settler-fields](../../su-api-enums/su.gamedata.md#settler-fields "mention")

#### Rückgabewert

* `number` – Der ausgelesene Wert des Siedlerfeldes

#### Beispiel

```lua
-- liest den Schaden, der von Bogenschützen Level 2 vom Maja verursacht wird, aus (ohne Kampfkraft-Skalierung)
local dmg = SU.GameData.GetSettlerInfo(SU.Tribes.MAYA, Settlers.BOWMAN_02, SU.GameData.SETTLER_FIELD_DAMAGE)
```
