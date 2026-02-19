---
description: by MuffinMario
---

# All Points in a circle/ring (hexagon)

## circle(x, y, radius, func)                    ![](<../../.gitbook/assets/circle2 (1).png>)

Führt die Funktion `func` auf der gesamten **Fläche** des Kreises (Hexagons) um die angegebenen Koordinaten im entsprechenden `radius` aus.

* `radius`: 0 nur aktuelles Feld, 1 für den ersten umliegenden Kreis, usw.
* `func`: wird mit den Parametern x,y des jeweiligen Punktes der Fläche aufgerufen

<details>

<summary>Beispiel: circle(x, y, radius, func)</summary>

```lua
function createSlimeball(x, y)
  Effects.AddEffect(Effects.SLIMEBALL, Sounds.NO_SOUND, x, y, 0)
end

function new_game()
    circle(128, 128, 5, createSlimeball)
end
```

oder in kurz und unleserlich

```lua
function new_game()
  circle(128,128,5,function(x,y)
                    Effects.AddEffect(Effects.SLIMEBALL,Sounds.NO_SOUND,x,y,0)
                  end
  )
end
```



```lua
function circle(x, y, radius, func)
    local r = radius + 1
    local xorig = x
    local yorig = y
    local iterations = 2 * r - 1
    local i = iterations
    local left = r - 1
    local right = 0
    while i > 0 do
        local cx = xorig - left;
        local cy = yorig + r - i;
        while cx <= xorig + right do
            func(cx,cy)
            cx = cx + 1
        end
        if right == r - 1 then
            left = left - 1
        else
            right = right + 1
        end
        i = i - 1
    end
end
```

</details>



## ring(x, y, radius, func)                       ![](<../../.gitbook/assets/ring2 (3).png>)

Führt die Funktion `func` auf dem **Umkreis** (Hexagons) um die angegebenen Koordinaten im entsprechenden `radius` aus.

* `radius`: 0 nur aktuelles Feld, 1 für den ersten umliegenden Kreis, usw.
* `func`: wird mit den Parametern x,y des jeweiligen Punktes des Umkreises aufgerufen

<details>

<summary>Beispiel: ring(x, y, radius, func)</summary>

```lua
function createSlimeball(x,y)
  Effects.AddEffect(Effects.SLIMEBALL,Sounds.NO_SOUND,x,y,0)
end

function new_game()
    ring(128,128,5,createSlimeball)
end
```

oder in kurz und unleserlich

```lua
function new_game()
  ring(128,128,5,function(x,y)
                    Effects.AddEffect(Effects.SLIMEBALL,Sounds.NO_SOUND,x,y,0)
                  end
  )
end
```



```lua
function ring(x, y, radius, func)
  local r = radius + 1
  local xorig = x
  local yorig = y
  local iterations = 2 * r - 1
  local i = iterations
  local left = r - 1
  local right = 0
  local row = 0
  while i > 0 do
    local cx = xorig - left
    local cy = yorig + r - i
    local last = (xorig + right) - cx
    local col = 0
    while cx <= xorig + right do
      if row == 0 or row == iterations - 1 then
        func(cx, cy)
      elseif col == 0 or col == last then
        func(cx, cy)
      end
      cx = cx + 1
      col = col + 1
    end
    if right == r - 1 then
      left = left - 1
    else
      right = right + 1
    end
    i = i - 1
    row = row + 1
  end
end
```

</details>
