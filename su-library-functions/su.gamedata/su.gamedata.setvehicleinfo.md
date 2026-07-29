---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.SetVehicleInfo

## SU.GameData.GetVehicleInfo(tribe, vehicleType, vehicleField)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

Setzt/überschreibt einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Fahrzeugs/Schiffs aus den aktuell im Spiel verwendeten Spieldaten.

#### Parameter

* `tribe`: [su.tribes.md](../../su-api-enums/su.tribes.md "mention")
* `vehicleType`: [vehicles.md](../../api-enums/vehicles.md "mention")
* `vehicleField`: [#vehicle-fields](../../su-api-enums/su.gamedata.md#vehicle-fields "mention")
* `value`: neuer Wert, der zugewiesen wird

#### Rückgabewert

* 1: erfolgreich
* -1: sonst / Fehler

#### Beispiel

```lua
-- setzt die Geschwindigkeit von NEU gebauten Kriegsschiffen der Römer auf 2
local success = SU.GameData.SetVehicleInfo(SU.Tribes.ROMAN, Vehicles.WARSHIP, SU.GameData.VEHICLE_FIELD_WALKSTEPS, 2)
```
