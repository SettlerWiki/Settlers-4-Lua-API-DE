---
description: 'Aktuelle Version: 0.5.0'
---

# SU Library (0.5.0)

Mit dieser SU Library, die direkt in Settlers United integriert ist, werden fortlaufend neue Lua-Funktionen  ( [Broken link](broken-reference "mention") ) und Lua-Enums ( [Broken link](broken-reference "mention") ) den Mappern zur Verfügung gestellt.

Wünsche und Vorschläge für neue Funktionalitäten können gerne über Discord mitgeteilt werden.



## Installation

**Keine explizite Installation benötigt**, da diese SU Library **automatisch mit Settlers United installiert wird!**



## NEU: "SUVars" statt "Vars" (momentan nur bei UBO-Test!)

Ab der SULib Version 0.5.0 ([su-library-0.5.0.md](su-library-0.5.0.md "mention")) gibt es die globale Tabelle "SUVars", die ähnlich funktioniert wie die bisherige Tabelle "Vars". Aber anstelle von 9 "Vars.SaveX" Variablen, wird (**momentan nur bei UBO-Test!**) mittels SU die **gesamte Tabelle SUVars abgespeichert und beim Laden wiederhergestellt (siehe** [#neu-suvars-statt-vars-momentan-nur-bei-ubo-test](su-library-0.5.0.md#neu-suvars-statt-vars-momentan-nur-bei-ubo-test "mention")**)**.

Die Tabelle SUVars kann wie jede andere verwendet werden und wird genau so wiederhergestellt, wie sie abgespeichert wurde.

Wichtig: Die Tabelle sollte nie im globalen Bereich beschrieben werden, da das die Tabelle bei jedem Laden überschreibt.

<details>

<summary>Beispiel-Code</summary>

```lua
-- Do NOT do this:
--SUVars["gameTime"] = 0    -- this OVERWRITES the saved value each time you load it!

-- Don't forget to initialize the values once!
function initVariables()
  SUVars["gameTime"] = -1
end

-- How to use it properly:
function fiveTicks()
  local time = Game.Time()
  if SUVars["gameTime"] < time then
    SUVars["gameTime"] = time  -- saves the last processed time
    -- do something here...
    dbg.stm(time)
  end
end

-- check for proper SULib version
function new_game()
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

</details>



## Version überprüfen

Neue Funktionen werden immer wieder zur SU Library hinzugefügt. Damit ein Skript, das auf Funktionen einer neueren Version basiert, als der Spieler lokal zur Verfügung hat, nicht abstürzt, sollte vorher auf die höchste Version der SU Library geprüft werden, die benötigt wird.

**Beispiel**: Wird die Funktion [game.areplayerareasconnected.md](../su-library-functions/game/game.areplayerareasconnected.md "mention") verwendet, steht oben auf der Seite der Funktion "`SU Library: erst ab Version 0.2.0 verfügbar!`", d.h. um diese Funktion fehlerfrei verwenden zu können, muss beim Spieler mindestens die `Version 0.2.0` vorhanden sein!

Der Einfachheit halber kann auch direkt auf die **neueste Version** geprüft werden, die zum Zeitpunkt der Erstellung des Skripts vorhanden war, die wird immer **auf dieser Seite ganz oben** sichtbar sein.

Das folgende Skript kann verwendet werden, um auf die entsprechende benötigte Version zu prüfen. Die Variable `requiredVersion` muss entsprechend angepasst werden.

**WICHTIG:** in Lua werden **Abfragen ohne rechter Seite auch bei 0 zu "true" evaluiert** (z.B. bei "**`if SU.VersionOK("0.0.0") then [body] end`**" wird der **`[body]`** immer ausgeführt, auch wenn die Funktion 0 zurückgibt! Daher immer "**`== 0`**" verwenden!)

```lua
function new_game()
  -- don't add anything in this function above these lines
  if SU then
    local requiredVersion = "0.3.0" -- TODO change this to the version your map-script requires
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
end
```

`SU.VERSION` - Gibt die aktuelle vollständige Version an (Beispiel: 0.2.1) \
`SU.MAJOR_VERSION` - Gibt die aktuelle **Haupt**version an (Beispiel: 0) \
`SU.MINOR_VERSION` - Gibt die aktuelle **Neben**version an (Beispiel: 2) \
`SU.AUTHOR` - Gibt die aktuellen Autoren an
