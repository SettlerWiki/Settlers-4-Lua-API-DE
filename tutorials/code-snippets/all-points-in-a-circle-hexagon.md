---
description: by MuffinMario
---

# All Points in a circle (hexagon)

Nutzung: `circle(x,y,radius,funktion mit parameter x,y)` Z.B.

```lua
function createSlimeball(x,y)
  Effects.AddEffect(Effects.SLIMEBALL,Sounds.NO_SOUND,x,y,0)
end

function new_game()
    circle(128,128,5,createSlimeball)
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
function circle(x,y,radius,func)

    local r = radius
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
        
        --inc/decs
        if right == r - 1 then
            left = left - 1
        else
            right = right + 1
        end
        
        i = i - 1
    end
end
```
