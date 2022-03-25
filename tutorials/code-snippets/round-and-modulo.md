---
description: by MuffinMario
---

# Round & Modulo

## floorNumber

Mit der folgenden Methode könnt ihr aus einer Kommazahl wieder ein Integer machen.\
Leider ist im Siedler lua Math nicht angebunden, daher hier die eigene Floor Methode

```lua
function floorNumber(floatNumber)
    local stringmyValue = tostring(floatNumber)
    if strfind(stringmyValue, "(%.+)") ~= nil then
        local valuestring = strsub(stringmyValue, 1, strfind(stringmyValue, "(%.+)"))
        return tonumber(valuestring)
    else
        return floatNumber
    end
end
```

## round & mymod

Basierend auf floorNumber kannst du mit diesen Funktionen Zahlen runden, sowie mit Hilfe des [Modulo ](https://de.wikipedia.org/wiki/Division\_mit\_Rest#Modulo)Operators den Rest ausgeben lassen.

```lua
function round(num)
  return floorNumber(num+0.5)
end
function mymod(a,b)
  return round((a/b - floorNumber(a/b)) * b)
end
```
