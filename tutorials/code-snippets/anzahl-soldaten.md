# Soldatenanzahl ermitteln

Mit diesen Funktionen könnt ihr die Anzahl an Soldaten einer Partei ermitteln.

\
Hiermit kannst du alle Soldaten getten, diese sich in einem Turm bzw. Burg befinden.

`function getUnitsInBuildings(playerId)`

Hiermit kannst du alle Soldaten außerhalb von Gebäuden getten.&#x20;

`getAmountOfPlayerUnitsWithoutBuildings(playerId)`

Hiermit kannst du alle Soldaten, egal ob in oder außerhalb von Gebäuden, getten.

`getAmountOfPlayerUnits(playerId)`\
\
**Wie verwende ich es?**\
Bei den oben genannten Funktionen kannst du sie so verwenden wie sie dort stehen. Du musst nur **playerId** mit der Parteinummer ersetzten.\
\
Du musst nichts anderes machen, als die unten stehenden Logic's irgendwo hin zu copy pasten. Am besten, um die Ordnung beizubehalten, unter dem gesammten Script.&#x20;

```lua
-- Gibt die Anzahl an Soldaten eines Spieler innerhalb seiner Tuerme und Burgen zureck
function getUnitsInBuildings(playerId)
	local allUnits = 0
	allUnits = allUnits + Buildings.Amount(playerId, Buildings.GUARDTOWERSMALL, Buildings.READY)
	allUnits = allUnits + Buildings.Amount(playerId, Buildings.GUARDTOWERBIG, Buildings.READY) * 6
	allUnits = allUnits + Buildings.Amount(playerId,Buildings.CASTLE, Buildings.READY) * 8
	return allUnits
end

-- gibt die Anzahl an Soldaten eines Spieler ohne die Soldaten innerhalb von Gebaeuden zurueck. 
function getAmountOfPlayerUnitsWithoutBuildings(playerId)
	local allUnitsWithoutBuilding = getAmountOfPlayerUnits(playerId)
	allUnitsWithoutBuilding = allUnitsWithoutBuilding - getUnitsInBuildings(playerId)
	return allUnitsWithoutBuilding
end 

-- gibt die Anzahl aller Soldaten eines Spielers zurueck
function getAmountOfPlayerUnits(playerId)
	local AmoutOfMilitary = 0
 	--Soldaten zaehlen	
	AmoutOfMilitary =  AmoutOfMilitary + Settlers.Amount(playerId, Settlers.SWORDSMAN_01) +  Settlers.Amount(playerId, Settlers.SWORDSMAN_02) + Settlers.Amount(playerId, Settlers.SWORDSMAN_03)
	-- Bogenschuetzen
	AmoutOfMilitary =  AmoutOfMilitary + Settlers.Amount(playerId, Settlers.BOWMAN_01) +  Settlers.Amount(playerId, Settlers.BOWMAN_02) + Settlers.Amount(playerId, Settlers.BOWMAN_03)
	-- Spezial Wiki
	AmoutOfMilitary = AmoutOfMilitary + Settlers.Amount(playerId, Settlers.AXEWARRIOR_01) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_02) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_03)
	-- Spezial Maya
	AmoutOfMilitary = AmoutOfMilitary + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_01) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_02) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03)
	-- Spezial Trojaner
	AmoutOfMilitary = AmoutOfMilitary + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_01)	+ Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_02) + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)
	-- Spezial Römer
	AmoutOfMilitary = AmoutOfMilitary + Settlers.Amount(playerId, Settlers.MEDIC_01) + Settlers.Amount(playerId, Settlers.MEDIC_02) + Settlers.Amount(playerId, Settlers.MEDIC_03)	
	-- Hauptmaenner
	AmoutOfMilitary = AmoutOfMilitary + Settlers.Amount(playerId, Settlers.SQUADLEADER) 	
	
	return AmoutOfMilitary 
end 
```
