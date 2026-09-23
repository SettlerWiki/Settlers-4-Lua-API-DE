---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.SetSettlerInfo

## SU.GameData.SetSettlerInfo(tribe, settlerType, settlerField, value)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Setzt/überschreibt einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Siedlers aus den aktuell im Spiel verwendeten Spieldaten.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `settlerField`: [#settler-fields](../../su-api-enums/su.gamedata.md#settler-fields "mention")
* `value`: neuer Wert, der zugewiesen wird

#### Rückgabewert

* 1: erfolgreich
* -1: sonst / Fehler

#### Beispiel

```lua
-- setzt den Schaden, der von Bogenschützen Level 2 vom Maja verursacht wird (ohne Kampfkraft-Skalierung) auf 20
local success = SU.GameData.SetSettlerInfo(SU.Tribes.MAYA, Settlers.BOWMAN_02, SU.GameData.SETTLER_FIELD_DAMAGE, 20)
```
