# Textnachricht nur für einen Spieler

Ihr könnt die Game.LocalPlayer() Funktion nutzen, um Nachrichten im Chat lediglich für einen Spieler darzustellen:

```lua
function privateMessage(playerid, msg)
	if Game.LocalPlayer() == playerid then
		dbg.stm(msg)
	end
end

function new_game()
	privateMessage(1, "Dies kann nur Spieler 1 lesen!")
	privateMessage(2, "Dies kann nur Spieler 2 lesen!")
end
```
