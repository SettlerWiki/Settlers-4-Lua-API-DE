# Löschen aller Gebäude

Im folgenden betrachten wir eine Funktion die alle Gebäude einer Partei zerstört.

```lua
function deleteallbuildings(partei)
	counter = 1
	x = 0
	while counter < 83 do		
		x = Buildings.Amount(partei,counter, Buildings.READY)
 
		while x~=0 do		
			Buildings.Delete(Buildings.GetFirstBuilding(partei,counter),partei)
			x = x-1
		end
		counter = counter +1		
	end
end
```

Die Funktion erwartet als Parameter die entsprechende Partei und kann so aufgerufen werden

`deleteallbuildings(2)`&#x20;

Falls man möchte dass alle Gebäude zerstört werden sollen außer Gründungsgebäude kann man die Funktion entsprechend anpassen:

```lua
function deleteallbuildings(partei)
	counter = 1
	x = 0
	while counter < 83 do
		if counter == 46 then
			counter=49
		end
		x = Buildings.Amount(partei,counter, Buildings.READY)
		while x~=0 do		
			Buildings.Delete(Buildings.GetFirstBuilding(partei,counter),partei)
			x = x-1
		end
		counter = counter +1		
	end
end
```

**Erklärung**: Alle Gebäude haben eine Nummer von 1 bis 83, man läuft über alle Gebäudeeinträge und löscht die entsprechende Anzahl der jeweiligen Gebäude. Die Gründungsgebäude, Kleiner Turm , Großer Turm und Burg haben die Nummern 46,47 und 48 weshalb wir diese im unteren Beispiel überspringen.<br>
