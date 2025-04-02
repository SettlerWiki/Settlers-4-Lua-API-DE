---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.StartPlacement

## SU.Buildings.StartPlacement(buildingType\[, playerID=localPlayer])

Startet das Platzieren des angegebenen Gebäudes für den optional angegebenen Spieler\*, als hätte er es im Menü ausgewählt.

#### Notiz

* \* Wird kein Spieler angegeben, wird dies für alle Spieler ausgeführt, die diese Funktion aufrufen. Das Lua-Skript läuft nämlich bei allen Menschen gleichzeitig, d.h. wenn keine selbsterstellten Checks eingebaut wurden, betrifft das alle menschlichen Spieler!

#### Notiz

* Mana-Gebäude werden automatisch dem Volk entsprechend umgewandelt, da es ansonsten zu Abstürzen kommt. D.h. dass z.B. "Buildings.AGAVEFARMERHUT" für den Römer automatisch zu "Buildings.VINYARD" wird.

#### Parameter

* `buildingType`: [.](./ "mention")
* `playerID [1-8]` (optional): Spieler-ID, **Index 0 ist ungültig!**

#### Beispiel

```lua
SU.Buildings.StartPlacement(Buildings.AGAVEFARMERHUT)    // betrifft alle menschlichen Spieler!
SU.Buildings.StartPlacement(Buildings.AGAVEFARMERHUT, 3)    // nur Spieler 3
```
