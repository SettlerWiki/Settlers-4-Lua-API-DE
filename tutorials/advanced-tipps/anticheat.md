# Anticheat

Mithilfe der Chat Eingabe **!incubation2** kann man im Single Player Modus die Cheats aktivieren. Gibt man dann **!win** ein gilt die Karte als gewonnen und wird aufgedeckt. Falls man nicht möchte dass der Spieler die Karte aufdeckt kann man das per Script verhindern.\
\
Ein solches Script könnte wie folgt aussehen&#x20;

```lua
function anticheat()           
	if Game.IsAlmostAllLandExplored() == 1 then
	Game.SetAlliesDontRevealFog(1)
	Game.ResetFogging()
        Tutorial.Exit()
	end
end
 
function TurnOnLandExploreCheck()
	Game.EnableLandExploredCheck(1)
end
 
function new_game()
	dbg.stm("Script Loaded")
       request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
       request_event(TurnOnLandExploreCheck,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
	request_event(anticheat,Events.FIVE_TICKS)
	request_event(cheathelp,Events.TICK)
end
 
function register_functions()
	reg_func(VictoryConditionCheck)
	reg_func(TurnOnLandExploreCheck)
	reg_func(anticheat)
	reg_func(cheathelp)
end
 
--//Beispiel Siegesbedingung, in diesem Fall besiege Spieler 2//--
function VictoryConditionCheck()
	Game.DefaultPlayersLostCheck()
	if Game.HasPlayerLost(1) == 0
	and Game.HasPlayerLost(2) == 1		
	and Game.HasPlayerLost(3) == 1
	and Game.HasPlayerLost(4) == 1
	and Game.HasPlayerLost(5) == 1
	then
		unrequest_event(anticheat,Events.FIVE_TICKS)
		Game.EnemyPlayersLost(1)
	end
	Game.DefaultGameEndCheck()
end
```

Dieses Besipiel ist natürlich nicht perfekt, die Verwendung der Funktion **Game.IsAlmostAllLandExplored()** bringt einige Nachteile mit sich. Sie kontrolliert wie viel Prozent der Karte mit Land vom Spieler bereits entdeckt wurde, also nicht schwarz ist. Erreicht diese Zahl die 95% wertet **Game.IsAlmostAllLandExplored() == 1** zu TRUE aus. Es ist hier also möglich die Anticheat-Funktion zu triggern ohne zu cheaten.\
\
Als nächstes betrachten wir die Möglichkeiten damit die Anticheat-Funktion nicht triggert ohne zu cheaten.\
\
Am einfachsten wäre es als Mapper eine unerreichbare Insel zu erstellen die mindestens 5% der Landmasse einnimmt. Man sollte hierbei beachten dass der Spieler nicht die Trojaner spielt und keine Maya als Gegner eingestellt sind da mit dem Zauber _**Orakel von Delphi**_ der Trojaner und _**Verbannung**_ der Maya diese Bedingung durchbrochen werden kann.\
\
Die am meisten Verwendete Option ist das Ausschalten der Anti-Cheat Funktion nach einem gewissen Zeitraum zum Beispiel 100 Minuten.\
Eine weitere Alternative wäre, dass man Funktion ausschaltet nachdem eine bestimmte Anzahl an Gegnern besiegt wurde. Bei 5 Gegner könnte man nach 2 besiegten Gegnern die Funktion abschalten. So könnte das ganze insgesamt aussehen&#x20;

```lua
function anticheat()           
	if Game.IsAlmostAllLandExplored() == 1 then
	Game.SetAlliesDontRevealFog(1)
	Game.ResetFogging()
       Tutorial.Exit()
	end
end
 
function cheathelp()
	if Game.Time() == 100 then
	unrequest_event(anticheat,Events.FIVE_TICKS)
	end
 
	if Game.HasPlayerLost(2) + Game.HasPlayerLost(3) + Game.HasPlayerLost(4) + Game.HasPlayerLost(5) > 1 then
	unrequest_event(anticheat,Events.FIVE_TICKS)
	end
end
 
function TurnOnLandExploreCheck()
	Game.EnableLandExploredCheck(1)
end
 
function new_game()
	dbg.stm("Script Loaded")
       request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
       request_event(TurnOnLandExploreCheck,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
	request_event(anticheat,Events.FIVE_TICKS)
	request_event(cheathelp,Events.TICK)
end
 
function register_functions()
	reg_func(VictoryConditionCheck)
	reg_func(TurnOnLandExploreCheck)
	reg_func(anticheat)
	reg_func(cheathelp)
end
 
--//Beispiel Siegesbedingung, in diesem Fall besiege Spieler 2//--
function VictoryConditionCheck()
	Game.DefaultPlayersLostCheck()
	if Game.HasPlayerLost(1) == 0
	and Game.HasPlayerLost(2) == 1		
	and Game.HasPlayerLost(3) == 1
	and Game.HasPlayerLost(4) == 1
	and Game.HasPlayerLost(5) == 1
	then
		unrequest_event(anticheat,Events.FIVE_TICKS)
		Game.EnemyPlayersLost(1)
	end
	Game.DefaultGameEndCheck()
end
```
