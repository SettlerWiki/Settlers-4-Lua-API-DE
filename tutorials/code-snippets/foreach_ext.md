---
description: by MuffinMario
---

# foreach\_ext

Wendet eine Function `f()` auf alle Elemente in einer Tabelle `t` an. Es können entsprechende zusätzliche Parameter mit übergeben werden für `f()`&#x20;

```lua
function foreach_ext (t, f, ...)
    local i, v = next(t, nil)
    while i do
      local args = arg
      tinsert(args,1,v)
      tinsert(args,1,i)
      
      local res = call(f,args)
      
      tremove(args,1); -- it is the same object hence remove it again
      tremove(args,1);
      
      if res then return res end
      i, v = next(t, i)
    end
end
```

Beispiel mit Parameterübergabe:

```lua
t = { 10,20,30 }
foreach_ext(t,function(i,v,msg) print(msg .. " " .. i .. " " ..v) end,"hello")
```
