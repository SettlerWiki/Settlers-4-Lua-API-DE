---
description: 'SU Library: erst ab Version 0.3.0 verfügbar!'
---

# SU.Settlers.AddSettlersIfNeeded

## SU.Settlers.AddSettlersIfNeeded(x, y, playerID, settlerType, amount\[, radius=20\[, checkLandOwnedRadius=1\[, withBeds=0]]])

Erzeugt Siedler an den angegebenen Koordinaten, wenn im Radius nicht genügend vorhanden sind.\
Zusätzlich können gleich entsprechende Betten hinzugefügt werden, damit diese neuen Siedler nicht zu Streikenden führen können.

Der hauptsächliche Nutzen dieser Funktion ist es, (KI-)Spielern "unendlich" Träger geben zu können, ohne dass tausende herumstehen, sich gegenseitig blockieren und dadurch zu Leistungseinfällen zu führen.

Z.B. kann diese Funktion jede Minute aufgerufen werden und im angegebenen Bereich auf 50 Träger "auffüllen". Wählt man einen Ort, wo sich normalerweise keine Träger aufhalten, kann die KI dadurch unendlich lange Soldaten produzieren.

#### Notiz

* der Spieler darf noch nicht verloren haben
* wie die anderen Funktionen auch, sollte gerade diese Funktion nicht zu häufig aufgerufen werden (nicht alle paar Ticks), sondern lieber seltener (z.B. jede Minute), das reicht in den allermeisten Fällen aus
* der Radius muss mit Bedacht gewählt werden. Ist er zu klein, sodass `amount` viele gar keinen Platz darin hätten, werden unendlich lange Siedler hinzugefügt und das Spiel wird früher oder später daran abstürzen!
* wird die Funktion dauerhaft ausgeführt, sollte `withBeds` **nicht** aktiviert sein, da dies endlos Betten hinzufügt. Besser wäre es, die Bettenanzahl einmalig zu einem hohen Wert zu setzen\
  ⇒ [game.areplayerareasconnected-3.md](../game/game.areplayerareasconnected-3.md "mention") bzw. [game.areplayerareasconnected.md](../game/game.areplayerareasconnected.md "mention")

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `amount`: Anzahl der hinzuzufügenden Siedler (inkl. Betten)
* `radius` (optional): Radius, in dem nach vorhandenen Siedlern gesucht wird. Um nicht endlos Siedler hinzuzufügen, muss der Radius **der Siedlermenge entsprechend groß genug** gesetzt werden!
* `checkLandOwnedRadius` (optional): Radius, in dem das Land dem Spieler gehören muss, um Siedler hinzuzufügen
* `withBeds` (optional): 1: Betten werden hinzugefügt, 0: ohne Betten

#### Rückgabewert

* Anzahl an hinzugefügten Siedlern
* -1: Fehler: das Land gehört dem Spieler nicht mehr oder er ist nicht mehr am Leben\
  ⇒ folglich sollte diese Funktion nicht mehr aufgerufen werden

#### Beispiel

```lua
local numAdded = SU.Settlers.AddSettlersIfNeeded(x, y, 3, Settlers.CARRIER, 50)	-- ensure radius is big enough!
```

```lua
-- to check for new minute
lastMinute = -1

function spawnCarriersPlayer1()
    currentMinute = Game.Time()
    if lastMinute ~= currentMinute then
        lastMinute = currentMinute
        local numAdded = SU.Settlers.AddSettlersIfNeeded(592, 510, 1, Settlers.CARRIER, 50)
        if numAdded == -1 then
            -- player dead or doesn't own this spot anymore -> stop spawning
            unrequest_event(ticking, Events.FIVE_TICKS)
        end
    end
end


function new_game()
    SU.Game.AddBeds(1, 2000)    -- add beds just once, not with every function call!
    request_event(spawnCarriersPlayer1, Events.FIVE_TICKS)
end

function register_functions()
    reg_func(spawnCarriersPlayer1)
end
```
