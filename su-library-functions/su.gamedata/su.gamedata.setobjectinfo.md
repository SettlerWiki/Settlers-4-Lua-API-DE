---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData.SetObjectInfo

## SU.GameData.SetObjectInfo(objectType, objectField, value)

{% hint style="info" %}
Siehe [.](./ "mention")
{% endhint %}

{% hint style="info" %}
Objekte speichern **nicht** die Dateien 1:1 aus der xml intern ab!
{% endhint %}

Setzt/überschreibt einen bestimmten Informationswert (Prototyp-Eigenschaft) eines Objekts aus den aktuell im Spiel verwendeten Spieldaten.

#### Parameter

* `objectType`: [su.objects.md](../../su-api-enums/su.objects.md "mention")
* `objectField`: [#object-fields](../../su-api-enums/su.gamedata.md#object-fields "mention")
* `value`: neuer Wert, der zugewiesen wird

#### Rückgabewert

* 1: erfolgreich
* -1: sonst / Fehler

#### Beispiel

```lua
-- entfernt die Eigenschaft hasPingPong hasPingPong vom Objekt
local success = SU.GameData.SetObjectInfo(SU.Objects.BUSH8, SU.GameData.OBJECT_FIELD_HASPINGPONG, 0)
```
