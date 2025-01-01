# Game.ArePlayerAreasConnected

## `Game.ArePlayerAreasConnected(ParteiA, X, Y, ParteiB, X, Y)`

Prüft, ob zwei Ecosektoren, die die angegebenen Koordinaten enthalten, miteinander verbunden sind. Eine Verbindung besteht auch dann, wenn die Gebiete durch einen verbündeten Spieler verbunden sind.

#### Rückgabewert

True oder False

#### Beispiel

```lua
Game.ArePlayerAreasConnected(1, 260, 279, 2, 98, 353)
```
