---
description: 'SU Library: erst ab Version 0.5.0 verfügbar!'
---

# SUVars: mehr speicherbare Variablen

## "SUVars" statt "Vars" (momentan nur bei UBO-Test!)

Es war noch nie einfacher, **Lua-Variablen über Speicherstände hinweg abzuspeichern** - ohne Installation oder externes Script - und zwar über "**SUVars**".

"**SUVars**" ist eine neue globale Tabelle in Lua, die **automatisch mit allen Einträgen** **abgespeichert und** beim Laden **wiederhergestellt** wird - ohne Namensvorgabe (Die Siedler 4 unterstützen bisher ja nur 9 "Vars.SaveX" Variablen).

⇒ D.h., alles was gesichert werden soll, muss einfach irgendwo in der Tabelle "**SUVars**" ablegt werden.&#x20;

Mit der richtigen Handhabung können so **auch dynamische Daten** abgespeichert werden.



## Verwendung

SUVars kann ganz normal wie jede andere Lua-Tabelle verwendet werden:

```lua
-- alle diese Beispiele sind Möglichkeiten, SUVars zu verwenden
SUVars["variableName"] = 123
SUVars.variableName = 456
SUVars["variableName"] = "Hey "
SUVars.variableName = "there!"
SUVars["variableName"] = {1, 2, 3, "4", "5"}
```

#### Notizen:

* Tabelleneinträge müssen einmalig(!) **initialisiert** werden, bevor sie abgefragt und/oder verglichen werden. Sonst wird "`nil`" zurückgegeben, was nicht mit anderen Werten außer "`nil`" verglichen werden kann.
* Die Tabelle **sollte nie** im **globalen** Bereich **beschrieben werden**, da das die Tabelle bei jedem Laden überschreibt.

#### Beispiel

```lua
-- Do NOT do this:
--SUVars["gameTime"] = 0    -- this OVERWRITES the saved value each time you load it!

--------------------------
-- How to use it properly:

-- Don't forget to initialize the values once!
function initVariables()
  SUVars["gameTime"] = -1
end

function fiveTicks()
  local time = Game.Time()
  if SUVars["gameTime"] < time then
    SUVars["gameTime"] = time  -- saves the last processed time
    -- do something here...
    dbg.stm(time)
    -- All of the following lines work:
    --SUVars["number1"] = 123
    --SUVars.number2 = 456
    --SUVars["str1"] = "Hey "
    --SUVars.str2 = "there!"
    --SUVars["subtable1"] = {1, 2, 3, "4", "5"}
  end
end

-- check for proper SULib version
function new_game()
  -- check for minimum SULib version
  -- don't add anything in this function above these lines
  if SU then
    local requiredVersion = "0.5.0"
    if SU.VersionOK(requiredVersion) == 0 then
      dbg.stm("SU Library Version requirement not met! The Map-Script needs at least Version "..requiredVersion..", you have Version "..SU.VERSION.."!")
      dbg.stm("Update (and restart The Settlers IV via) Settlers United to get the latest Version installed.")
      return
    end
  else
    dbg.stm("SU Library is missing!")
    dbg.stm("Update (and restart The Settlers IV via) Settlers United to get the latest Version installed.")
    return
  end
  
  -- SU Library loaded and required Version fulfilled
  -- add your normal code here...
  request_event(initVariables, Events.FIRST_TICK_OF_NEW_GAME)
  request_event(fiveTicks, Events.FIVE_TICKS)
end

function register_functions()
  reg_func(initVariables)
  reg_func(fiveTicks)
end
```
