# Random innerhalb Bereich

Gibt eine Zufallszahl innerhalb eines Bereichs zurück.

**Verwendung**

`randomBetween(fromNumber, toNumber)`

Du kannst diese ohne benötigte Installation verwenden, das einzige was du machen musst, ist die Logic unter deinem Script zu platzieren.\
\
Du kannst die Funktion verwenden, indem du angibst, in welchen Bereich er eine Zufallszahl zurückgeben soll. z.B.:

`randomBetween(10,20)`

Gibt eine Zahl zwischen 10 und 20 zurück.

```lua
function randomBetween(fromNumber, toNumber)
	local divNumber = toNumber - fromNumber
	local randomNumber = fromNumber + Game.Random(divNumber + 1) 
	return randomNumber
end
```
