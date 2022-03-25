# Buildings.Amount

## `Buildings.Amount(Partei, Gebäudetyp, Status)`

Überprüft, wie viele Gebäude der angegebene Spieler vom angegebenen Typ besitzt. Dabei wird in Baustellen und fertige Gebäude unterschieden.

#### Rückgabewert

Anzahl der Gebäude

#### Beispiel

```lua
Buildings.Amount(2, Buildings.CASTLE, Buildings.READY)
Buildings.Amount(2, Buildings.CASTLE, Buildings.UNDERCONSTRUCTION)
```
