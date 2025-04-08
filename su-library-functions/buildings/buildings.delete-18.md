---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.UnGarrisonWarriors

## SU.Buildings.UnGarrisonWarriors(buildingID\[, index=-1, bowman=0])

Gibt den entsprechenden Soldaten im durch die ID angegebenen Gebäude den Auftrag, jenes zu verlassen.

#### Notiz

* Der Parameter "index" tut nicht wirklich das, was er tun sollte, die Ursache ist noch unbekannt. \
  **Wird diese Funktion mehrfach mit dem gleichen Index (außer -1) aufgerufen, entsteht ein FE!**\
  ⇒ **Daher sollte diese Funktion momentan nur mit "index = -1" verwendet werden, wodurch alle Soldaten das Gebäude verlassen** (bis auf der erste Schwertkämpfer)**!**

#### Parameter

* `buildingID`: ID des Gebäudes
* `index [-1, 0-5]` (optional): Index des Soldaten, der das Gebäude verlassen soll \[-1, 0, ...] (**Indizes starten bei 0**). Bei -1 verlassen alle Soldaten das Gebäude (bis auf der erste Schwertkämpfer), der Parameter `bowman` wird dabei ignoriert.
* `bowman [0-1]` (optional): ob (`0`) Schwertkämpfer oder (`1`) Bogenschützen das Gebäude verlassen sollen

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass die entsprechenden Soldaten das Gebäude verlassen haben, z.B. wenn es kein Militärgebäude war!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.UnGarrisonWarriors(buildingID)    // alle Soldaten verlassen das Gebäude
```
