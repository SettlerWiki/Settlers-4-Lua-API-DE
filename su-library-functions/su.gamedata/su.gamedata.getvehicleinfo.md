---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.GetVehicleInfo

## SU.GameData.GetVehicleInfo(tribe, vehicleType, vehicleField)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Liest einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Fahrzeugs/Schiffs aus den aktuell im Spiel verwendeten Spieldaten aus.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention")
* `vehicleField`: [#vehicle-fields](../../su-api-enums/su.gamedata.md#vehicle-fields "mention")

#### Rückgabewert

* `number` – Der ausgelesene Wert des Fahrzeugfeldes

#### Beispiel

```lua
-- liest die Geschwindigkeit vom Kriegsschiff der Römer aus
local speed = SU.GameData.GetVehicleInfo(SU.Tribes.ROMAN, Vehicles.WARSHIP, SU.GameData.VEHICLE_FIELD_WALKSTEPS)
```
