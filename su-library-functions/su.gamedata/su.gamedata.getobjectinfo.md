---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.GetObjectInfo

## SU.GameData.GetObjectInfo(objectType, objectField)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

{% hint style="info" %}
Objekte speichern **nicht** die Dateien 1:1 aus der xml intern ab!
{% endhint %}

Liest einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Objekts aus den aktuell im Spiel verwendeten Spieldaten aus.

#### Parameter

* `objectType`: [su.objects.md](../../su-api-enums/su.objects.md "mention")
* `objectField`: [#object-fields](../../su-api-enums/su.gamedata.md#object-fields "mention")

#### Rückgabewert

* `number` – Der ausgelesene Wert des Objektfeldes

#### Beispiel

```lua
-- liest aus, ob das Objekt die Eigenschaft hasPingPong hat
local hasPingPong = SU.GameData.GetObjectInfo(SU.Objects.BUSH8, SU.GameData.OBJECT_FIELD_HASPINGPONG)
```
