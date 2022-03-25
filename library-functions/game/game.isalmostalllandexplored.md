# Game.IsAlmostAllLandExplored

## `Game.IsAlmostAllLandExplored()`

Gibt an, ob die meiste Landfläche bereits erkundet wurde. Wie viel % Land genau erkundet werden muss ist unklar

{% hint style="info" %}
Es muss der Land Explore Check vor dem Aufruf aktiviert worden sein. (siehe [Game.EnableLandExploredCheck](game.enablelandexploredcheck.md))
{% endhint %}

#### Rückgabewert

1 wenn die meiste Landfläche erkundet wurde, ansonsten 0

#### Beispiel

```lua
-- einmalig
Game.EnableLandExploredCheck()

-- danach immer möglich zu benutzen
if Game.IsAlmostAllLandExplored() == 1 then
  dbg.stm("Fast alles an Land wurde erkundet.")
end
```
