---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetUniqueID

## SU.Entity.GetUniqueID(entityID)

Gibt die **"eindeutige ID**" der Entität zurück - **nicht in S4-Funktionen verwendet!**



**ACHTUNG:** In **Siedler 4** wird in allen Funktionen ausschließlich die "normale ID" (`entityID`) der Entity verwendet - **nicht die hier zurückgegebene "eindeutige ID"!**



Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).



#### Hintergrund

Entitäten besitzen in Wirklichkeit **zwei verschiedene IDs**:

* **normale ID**:\
  Diese ID wird von allen Spiel-Funktionen verwendet. Sie ist zu einem bestimmten Zeitpunkt eindeutig, wird jedoch **nach dem Tod der Entität wiederverwendet!**\
  → Das bedeutet: Wenn man eine normale ID über längere Zeit (z. B. über mehrere Ticks) speichert, kann man **nicht garantieren**, dass sie später noch zur gleichen Entität gehört!
*   **eindeutige ID**:

    Diese ID ist **dauerhaft einzigartig und wird niemals erneut vergeben** – sie bleibt also über die gesamte Laufzeit hinweg eindeutig.



#### Zweck dieser Funktion

Diese Funktion richtet sich speziell an Mapper, die normale IDs über längere Zeiträume speichern möchten und dabei sicherstellen wollen, dass eine gespeicherte ID **immer noch zur ursprünglichen Entität** gehört, um nicht alle paar Ticks wieder alle Entitäten durchiterieren zu müssen.\
Durch einen Abgleich zwischen vorheriger und jetziger **eindeutigen ID** kann diese Zuordnung überprüft werden.

<details>

<summary>Beispiel Skript</summary>

```lua
firstTowerID = 0
lastGameMinute = -1
idMap = {}

-- register pair {entityID, uniqueID}
function regID(entityID)
  local uniqueID = SU.Entity.GetUniqueID(entityID)
  if uniqueID ~= 0 then -- entity still exists
    idMap[entityID] = uniqueID
  end
end

-- checks if {entityID} is still valid (and was registered)
function checkID(entityID)
  local uniqueID = SU.Entity.GetUniqueID(entityID)
  if uniqueID ~= 0 then -- entity still exists
    local previousUniqueID = idMap[entityID]
    if previousUniqueID ~= nil then -- entityID was registered
      if previousUniqueID == uniqueID then
        return 1
      end
    end
  end
  return 0
end

function five_ticks()
  local time = Game.Time()
  if lastGameMinute ~= time then -- new minute
    lastGameMinute = time
    
    -- check if ID still valid
    if checkID(firstTowerID) == 0 then  -- NOT valid
      dbg.stm("ID is not longer valid!")
    else  -- valid
      dbg.stm("ID still valid!")
    end
  end
end

function new_game()
  -- don't add anything in this function above these lines
  if SU then
    local requiredVersion = "0.2.0" -- change this to the version your map-script requires
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
  firstTowerID = Buildings.GetFirstBuilding(1, Buildings.GUARDTOWERSMALL)
  regID(firstTowerID)
  
  request_event(tick, Events.FIVE_TICKS)
end

function register_functions()
  reg_func(five_ticks)
end

```



</details>



#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* **"eindeutige ID"** der Entität

#### Beispiel

```lua
local uniqueID = SU.Entity.GetUniqueID(entityID)
```
