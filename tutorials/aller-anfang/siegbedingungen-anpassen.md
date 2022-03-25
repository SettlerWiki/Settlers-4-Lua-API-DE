# Siegbedingungen anpassen

Ihr könnt für eure Karten selbst definierte Siegbedingungen schreiben. Das Spiel hat hierfür extra ein [spezielles Event](entrypoint-register\_functions-events-1.md), welches ähnlich wie **Events.FIVE\_TICKS** alle Fünf Ticks aufgerufen wird. Standartmäßig ist dieses Event jedoch von einer eigenen Funktion von Siedler belegt, welche ihr durch setzen dieses Events überschreibt.&#x20;

Dies ist das normale Verhalten von Siedler im Bezug auf die Überprüfung ob wer gewonnen hat:

```lua
function new_game()
       request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
end
 
function register_functions()
	reg_func(VictoryConditionCheck)
end

function VictoryConditionCheck()
	Game.DefaultPlayersLostCheck()
	Game.DefaultGameEndCheck()
end
```

Wenn ihr dort anstelle der **VictoryConditionCheck** nun einfach folgendes schreibt, dann führt dies dazu das selbst ein Spieler, der seinen letzten Turm abreißt, nicht verloren hat. Aber auch kein anderer Spieler somit gewinnen kann.&#x20;

```lua
function VictoryConditionCheck()
    -- ja hier muss nichts stehen für das beschriebe Beispiel!
end
```



Ihr könnt somit aber auch die Sieg & Niederlagebedingungen umschreiben. Als Beispiel könnt ihr überprüfen, ob bereits ein anderen Spieler verloren hat, und wenn ja verliert automatisch sein Teammate mit (Beispiel bei einem 2vs2):

```lua
function VictoryConditionCheck()
	Game.DefaultPlayersLostCheck()
	
	if Game.HasPlayerLost(1) == 1 then
		Game.PlayerLost(2)
	elseif Game.HasPlayerLost(2) == 1 then
		Game.PlayerLost(1)
	elseif Game.HasPlayerLost(3) == 1 then
		Game.PlayerLost(4)
	elseif Game.HasPlayerLost(4) == 1 then
		Game.PlayerLost(3)
	end
	Game.DefaultGameEndCheck()
end
```

\


