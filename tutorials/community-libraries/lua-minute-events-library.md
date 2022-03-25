---
description: by MuffinMario
---

# MinuteEvents-Library

{% embed url="https://github.com/MuffinMario/Siedler-4-Lua-Minute-Events-Library" %}

<details>

<summary>MinuteEvents.lua</summary>

{% code title="MinuteEvents.lua" %}
```lua
MinuteEvents =  {
  -- table of all events at all minutes in format _minuteEventTable[minute][funcid (from 1 - n; no specific meaning)]
  _minuteEventTable = {}
}

-- calls all function types in table
function MinuteEvents._subroutine_foreachFunction(i,v)
    if type(v) == "function" then
        v();
    end
end
function MinuteEvents.runMinuteEventTick()
  -- true on first tick of new minute
  local currentMinute = Game.Time()
  if Vars.Save9 ~= currentMinute then
    Vars.Save9 = currentMinute  -- minute
    -- calls all functions in table
    if MinuteEvents._minuteEventTable[Vars.Save9] ~= nil then
      foreach(MinuteEvents._minuteEventTable[Vars.Save9],MinuteEvents._subroutine_foreachFunction)
    end
  end

end

-- sets Save9 to 0 on start
function MinuteEvents.initVars()
  Vars.Save9 = 0
end
function MinuteEvents.new_game()
  request_event(MinuteEvents.runMinuteEventTick,Events.TICK)
  request_event(register_minute_events,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
  request_event(MinuteEvents.initVars,Events.FIRST_TICK_OF_NEW_GAME)
end
function MinuteEvents.register_functions()
  reg_func(MinuteEvents.runMinuteEventTick)
  reg_func(MinuteEvents.initVars)
  reg_func(register_minute_events)
end

-- util function to use
function requestMinuteEvent(eventfunc,minute)
  if MinuteEvents._minuteEventTable[minute] == nil then
    MinuteEvents._minuteEventTable[minute] = {}
  end
  tinsert(MinuteEvents._minuteEventTable[minute],eventfunc)
end
```
{% endcode %}

</details>

## Siedler-4-Lua-Minute-Events-Library

Eine easy-to-use library zum benutzen von callback funktionen die zu bestimmten Minuten aufgerufen werden

## Benutzung

* in deine new\_game Funktion musst du die Funktion `MinuteEvents.new_game()` aufrufen
* in deine register\_functions Funktion musst du die Funktion `MinuteEvents.register_functions()` aufrufen
* du benötigst eine Funktion mit dem Namen `register_minute_events()`, in der du die Funktionen, die zu bestimmten Minuten einmalig aufgerufen werden sollen registrierst

## Beispiel

````lua
-- ... füge hier die library ein

function new_game()
  MinuteEvents.new_game()
end

function register_functions()
  MinuteEvents.register_functions()
end

function testFunc()
  dbg.stm("testfunc")
end

function register_minute_events()
  requestMinuteEvent(testFunc,5)
end```
````

