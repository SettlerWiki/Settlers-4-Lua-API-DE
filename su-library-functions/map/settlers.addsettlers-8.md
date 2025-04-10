---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.IsDarkLandBorder

## SU.Map.IsDarkLandBorder(x, y)

Gibt zurück, ob die angegebenen Koordinaten eine Grenze zum Dunklen Land ist oder nicht.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* 1: es ist eine Grenze zum Dunklen Land
* 0: sonst / Fehler

#### Beispiel

```lua
local isDarkLandBorder = SU.Map.IsDarkLandBorder(x, y)
```
