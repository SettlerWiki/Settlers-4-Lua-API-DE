# Neue Minute angebrochen

Die folgende Methode gibt einmalig 1 zurück, sobald eine neue Minute angebrochen ist.

```lua
function newMinute()
	if Vars.Save8 ~= Game.Time() then
		Vars.Save8 = Game.Time()
		return 1
	else
		return 0
	end
end
```

Damit ist es möglich verschiedene Dinge jede Minute passieren zu lassen. Ihr könnt z.B. folgendes implementieren.\
\
Innerhalb einer Methode die regelmäßig (Ticks) aufgerufen wird.

```lua
function gameloop()
    if newMinute() == 1 then
	doEveryMinuteTask() 
    end
end
function new_game()
	request_event(gameloop, Events.FIVE_TICKS)
end
function register_functions()
	reg_func(gameloop)
end
```
