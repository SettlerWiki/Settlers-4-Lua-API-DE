# Game.EnableLandExploredCheck

## `Game.EnableLandExploredCheck(`)

Aktiviert den Land Explored Check, welcher die Funktion Game.IsAlmostAllLandExplored() ermöglicht zu überprüfen, ob fast alles an Land erkundet wurde.

#### Rückgabewert

none

#### Beispiel

```lua
-- einmalig
Game.EnableLandExploredCheck()

-- danach immer möglich zu benutzen
if Game.IsAlmostAllLandExplored() == 1 then
  dbg.stm("Fast alles an Land wurde erkundet.")
end
```
