---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.mod

## SU.Math.mod(x, y)

Berechnet den **Ganz**zahl-Rest der Division (Integer-Modulo `%`).

> **Hinweis:** Konvertiert **Fließkomma**zahlen **vor** der Berechnung in **ab**gerundete Ganzzahlen (Integer).

#### Parameter

* `x`: `number` – Der Dividend (wird als Integer verarbeitet)
* `y`: `number` – Der Divisor (wird als Integer verarbeitet)

#### Rückgabewert

* `number` – Der Integer-Rest der Division (`x % y`)

#### Beispiel

```lua
local modValue = SU.Math.mod(10, 3)     -- liefert 1
local floatMod = SU.Math.mod(5.7, 2.3)  -- schneidet Nachkommastellen ab (5 % 2) und liefert 1
```
