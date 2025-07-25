---
description: by Phottor
---

# Turnier Map Script 2vs2 2022

```lua
-----------------------------------------------
-----------------------------------------------
--Script for Settlers IV 2v2 tournament 2022---
-----------------HAVE FUN ---------------------
-----------------------------------------------
-----------------------------------------------

-- diagonals [1 = wall, 0 = no wall] 

mapsize = 1024
longdiagonal = 1
shortdiagonal = 0
horizontal = 0
vertical = 0

team1 = {1,2}
team2 = {3,4}
spectator = {5,6,7,8}

pt = 60
sabopt = 75

blockTowering = 0	-- 0 Off, 1 until pt, 2 until saboPt, 3 forever
blockToweringAxis = 0	-- 0 none, 1 short, 2 long, 3 both diagonal, 4 horizontal, 5 vertical, 6 both horizontal

-- only needed if blockTowering is off/0
towerradius = 33
effectradius = 8

welcome = 1
welcomemessage = "Peacetime Script active! Have fun!"

pt60units = {
	Settlers.PIONEER, Settlers.SABOTEUR, Settlers.PIONEER,
	Settlers.GARDENER, Settlers.SWORDSMAN_01, Settlers.SWORDSMAN_02,
	Settlers.SWORDSMAN_03, Settlers.BOWMAN_01, Settlers.BOWMAN_02,
	Settlers.BOWMAN_03, Settlers.AXEWARRIOR_01, Settlers.AXEWARRIOR_02,
	Settlers.AXEWARRIOR_03, Settlers.BLOWGUNWARRIOR_01,
	Settlers.BLOWGUNWARRIOR_02, Settlers.BLOWGUNWARRIOR_03,
	Settlers.BACKPACKCATAPULTIST_01, Settlers.BACKPACKCATAPULTIST_02,
	Settlers.BACKPACKCATAPULTIST_03, Settlers.MEDIC_01, Settlers.MEDIC_02,
	Settlers.MEDIC_03, Settlers.SQUADLEADER, Settlers.PRIEST
}

pt60vehicles = {
	Vehicles.WARSHIP,
	Vehicles.FERRY,
	Vehicles.WARMACHINE,
	Vehicles.CART
}

pt90units = {
	Settlers.SABOTEUR, Settlers.PIONEER
}

pt90vehicles = {
	Vehicles.WARSHIP,
	Vehicles.WARMACHINE,
}

towers = {0,0,0,0,0,0,0,0}
warns = {0,0,0,0,0,0,0,0}
state = 1 -- state (1: <pt, 2: <sabopt, 3: >sabopt)

function new_game()
	-- don't add anything in this function above these lines
	if SU then
		local requiredVersion = "0.4.0"
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

    request_event(initGame, Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
	request_event(winCondition, Events.VICTORY_CONDITION_CHECK)
    request_event(ticking, Events.FIVE_TICKS)
end

function register_functions()
    reg_func(initGame)
    reg_func(winCondition)
    reg_func(ticking)
end

function winCondition()
    ---killSpecators
	local player = 1
	local dead1 = 1
	local dead2 = 1
	while player <= getn(team1) do
		Game.DefaultPlayerLostCheck(team1[player])
		if Game.HasPlayerLost(team1[player]) == 1 then
			
		else
			dead1 = 0
		end
		player = player + 1
	end
	player = 1
	while player <= getn(team2) do
		Game.DefaultPlayerLostCheck(team2[player])
		if Game.HasPlayerLost(team2[player]) == 1 then

		else
			dead2 = 0
		end	
		player = player + 1
	end	
	
	if dead1 == 1 or dead2 == 1 then
		player = 1
		while player <= getn(spectator) do
			Game.PlayerLost(spectator[player])
			player = player + 1
		end
	end
	
    Game.DefaultGameEndCheck()
end

--- Ein Debug schalter.
function isDebug()
	return 0;
end

blockToweringEnabled = 0	-- do NOT change
function initGame()
	if welcome == 1 then
		local ptmessage = " (PT" .. pt .. ", SaboPT" .. sabopt .. ")"
		dbg.stm(welcomemessage .. ptmessage)
	end
	local player = 1
	while player <= 8 do
		dbg.aioff(player)
		if isIn(Game.LocalPlayer(), spectator) == 1 then
			Tutorial.RWM(1)
		end
		player = player + 1
	end
	
	if blockTowering ~= 0 then
		blockToweringEnabled = 1
		SU.Game.BlockToweringOverAxis(1, blockToweringAxis)
	end
end

function isIn(player, team)
	local index = 1
	while index <= getn(team) do
		if player == team[index] then
			return 1
		end
		index = index + 1
	end
	return 0
end

function isLocalPlayerSpectatorOrInTeamWith(player)
	if (isIn(player, team1) == 1 and isIn(Game.LocalPlayer(), team1) == 1) or (isIn(player, team2) == 1 and isIn(Game.LocalPlayer(), team2) == 1) or isIn(Game.LocalPlayer(), spectator) == 1 then
		return 1
	end
	return 0
end

ticksInit = 0
ticksPtWall = 0
ticksStati = 0
statiTurn = 1
function ticking()
	ticksPtWall = ticksPtWall + 5
	ticksStati = ticksStati + 5
    if ticksPtWall >= 35 then
		ticksPtWall = 0
		ptWall()
	end
	local threshhold = 210
	if getn(team1) + getn(team2) > 4 then
		threshhold = 420
	end
	if ticksStati >= threshhold then
		ticksStati = 0
		if isIn(Game.LocalPlayer(), spectator) == 1 then
			dbg.stm("--------")
			if getn(team1) + getn(team2) <= 4 then
				printMsgForTeam(team1)
				printMsgForTeam(team2)
			else
				if statiTurn == 1 then
					statiTurn = 2
					printMsgForTeam(team1)
					printMsgForTeam(team2)
				elseif statiTurn == 2 then
					statiTurn = 1
					printMsgForTeam(team2)
					printMsgForTeam(team1)
				end
			end
		end
	end
	
	if ticksInit < 30 then
		ticksInit = ticksInit + 5
	end
	if ticksInit == 30 then
		ticksInit = ticksInit + 5
		destroySpectators()
	end
end

function printMsgForTeam(team)
	local player = 1
	while player <= 8 do
		if isIn(player, team) == 1 then
			printMsgForPlayer(player)
		end
		player = player + 1
	end
end

function printMsgForPlayer(player)
	local AmountOfMilitary1 = Settlers.Amount(player, Settlers.SWORDSMAN_01)+
		Settlers.Amount(player, Settlers.BOWMAN_01)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_01)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_01)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_01)+
        Settlers.Amount(player, Settlers.MEDIC_01)

	local AmountOfMilitary2 = Settlers.Amount(player, Settlers.SWORDSMAN_02)+
		Settlers.Amount(player, Settlers.BOWMAN_02)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_02)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_02)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_02)+
        Settlers.Amount(player, Settlers.MEDIC_02)

    local AmountOfMilitary3 = Settlers.Amount(player, Settlers.SWORDSMAN_03)+
		Settlers.Amount(player, Settlers.BOWMAN_03)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_03)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_03)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_03)+
        Settlers.Amount(player, Settlers.MEDIC_03)+
        Settlers.Amount(player, Settlers.SQUADLEADER)

    local playerKills = Statistic.UnitsDestroyed(player)
    local playerSettlers = Settlers.Amount(player, Settlers.CARRIER)
    local playerOffenceFightingStrength = Game.GetOffenceFightingStrength(player)
    local playerMagic = Magic.CurrentManaAmount(player)
    local playerSABOTEUR = Settlers.Amount(player, Settlers.SABOTEUR)
    local playerTHIEF = Settlers.Amount(player, Settlers.THIEF)
    local playerResBuilt = ressourcesBuilt(player)
	
    if isIn(Game.LocalPlayer(), spectator) == 1 then
		dbg.stm("Min" .. Game.Time() .. " P" .. player .. " [" .. 
			getTextForPlayerRace2(player) .. "]: " .. (AmountOfMilitary1+AmountOfMilitary2+AmountOfMilitary3) .. " - " ..
            AmountOfMilitary1 .. "/ " .. AmountOfMilitary2 .. "/ " .. AmountOfMilitary3 .. " Soldiers | " .. playerKills .. " Kills | " ..
            playerSettlers .. " Settlers | " .. playerOffenceFightingStrength .. " KK | " ..
            playerMagic .. " Mana | " .. playerSABOTEUR .. " Sabos | " .. playerTHIEF .. " Thieves | " ..
            playerResBuilt .. " Res")
    end
end

function ptWall()
	-- state (1: 60, 2: 90, 3: >90)
	if Game.Time() < pt then
		state = 1
	elseif Game.Time() < sabopt then
		state = 2
		
		-- remove blockTowering
		if blockTowering == 1 then
			blockTowering = 0
			SU.Game.BlockToweringOverAxis(0, blockToweringAxis)
		end
	else
		state = 3
		
		-- remove blockTowering
		if blockTowering ~= 0 then
			blockTowering = 0
			SU.Game.BlockToweringOverAxis(0, blockToweringAxis)
		end
	end
	
	if state < 3 then
		towers = {0,0,0,0,0,0,0,0}
		if longdiagonal == 1 then
			WallCalcLong()
		end
		if shortdiagonal == 1 then
			WallCalcShort()
		end
		if horizontal == 1 then
			WallCalcHorizontal()
		end
		if vertical == 1 then
			WallCalcVertical()
		end
		
		if blockToweringEnabled == 0 then
			towerLogic()
		end
	end
end

function towerLogic()
	local player = 1
	while player <= 8 do
		if towers[player] == 1 then
			warns[player] = 1
			if isLocalPlayerSpectatorOrInTeamWith(player) == 1 then
				dbg.stm("Player " .. player .. " is building an illegal tower! Finishing this tower will be considered as a loss!")
			end
			ticksStati = 0
		end
		if towers[player] == 2 then
			warns[player] = 1
			dbg.stm("Player " .. player .. " built an illegal tower! This game is now considered as a loss for his team!")
			ticksStati = 0
		end
		if towers[player] == 0 and warns[player] == 1 then
			warns[player] = 0
			if isLocalPlayerSpectatorOrInTeamWith(player) == 1 then
				dbg.stm("Player " .. player .. " destroyed the illegal tower, situation defused (min " .. Game.Time() .. ").")
			end
			ticksStati = 0  
		end
		player = player + 1
	end
end

function WallCalcLong()
	local x = effectradius
	local y = mapsize - effectradius
	while (x <= (mapsize - effectradius)) do
		WallCalcHelper(x,y)
        x = x + effectradius
        y = y - effectradius
    end
end

function WallCalcShort()
	local x = effectradius
	local y = effectradius
	while (x <= (mapsize - effectradius)) do
		WallCalcHelper(x,y)
        x = x + effectradius
        y = y + effectradius
    end
end

function WallCalcHorizontal()
	local x = effectradius
	local y = mapsize / 2
	while (x <= (mapsize - effectradius)) do
		WallCalcHelper(x,y)
        x = x + effectradius
    end
end

function WallCalcVertical()
	local x = mapsize / 2
	local y = effectradius
	while (y <= (mapsize - effectradius)) do
		WallCalcHelper(x,y)
        y = y + effectradius
    end
end

function WallCalcHelper(x,y)
	blocktowers(x,y)
	if (towers[1] == 1 or towers[2] == 1 or towers[3] == 1 or towers[4] == 1 or towers[5] == 1 or towers[6] == 1 or towers[7] == 1 or towers[8] == 1) then
		if blockToweringEnabled == 0 then
			DrawEffects(x,y,Effects.MAGIC_PILE02,towerradius)
		end
	end
	if state == 2 then 
		removeVehiclesNearPoint(x,y,effectradius,pt90vehicles)
		removeUnitsNearPoint(x,y,effectradius,pt90units)
	elseif state == 1 then 
		removeVehiclesNearPoint(x,y,effectradius,pt60vehicles)
		removeUnitsNearPoint(x,y,effectradius,pt60units)
		DrawEffects(x,y,Effects.RMAGIC_JUPITERSLIGHTNING,effectradius)
	end
end

function DrawEffects(x,y,effect,radius)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y-radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y+radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x-radius,y-radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x-radius,y,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x+radius,y,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x+radius,y+radius,7)
end

function blocktowers(x,y)
	local player = 1
	while player <= 8 do 
		if Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERSMALL,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0	or
				Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERBIG,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0 or
				Buildings.ExistsBuildingInArea(player,Buildings.CASTLE,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0 then
			towers[player] = 1
		end
		if Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERSMALL,x,y,towerradius, Buildings.READY) > 0	or
				Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERBIG,x,y,towerradius, Buildings.READY) > 0 or
				Buildings.ExistsBuildingInArea(player,Buildings.CASTLE,x,y,towerradius, Buildings.READY) > 0 then
			towers[player] = 2
		end
		player = player + 1
	end
end

function removeVehiclesNearPoint(x,y,radius,vehicles)
    local index = 1
	while index <= getn(vehicles) do
		local player = 1
		while player <= getn(team1) do
			removeVehicleNearPoint(x,y,vehicles[index],radius,team1[player])
			player = player + 1
		end
		player = 1
		while player <= getn(team2) do
			removeVehicleNearPoint(x,y,vehicles[index],radius,team2[player])
			player = player + 1
		end
        index = index + 1
    end
end

function removeVehicleNearPoint(x,y,vehicle,radius,player)
	if Vehicles.AmountInArea(player, vehicle, x, y, radius) > 0 then
		Vehicles.KillVehicles(player, vehicle, x, y, radius)
		
		if isLocalPlayerSpectatorOrInTeamWith(player) == 1 then
			dbg.stm("Player " .. player .. " lost a vehicle to the PT wall (min " .. Game.Time() .. ")")
		end
		ticksStati = 0
    end
end

function removeUnitsNearPoint(x,y,radius,units)
    local index = 1
	while index <= getn(units) do
		local player = 1
		while player <= getn(team1) do
			removeUnitNearPoint(x,y,units[index],radius,team1[player])
			player = player + 1
		end
		player = 1
		while player <= getn(team2) do
			removeUnitNearPoint(x,y,units[index],radius,team2[player])
			player = player + 1
		end
        index = index + 1
    end
end

function removeUnitNearPoint(x,y,unit,radius,player)
	local amount = Settlers.AmountInArea(player,unit,x,y,radius)
	if amount > 0 then
		Settlers.KillSelectableSettlers(player,unit,x,y,radius, 0)
		if isLocalPlayerSpectatorOrInTeamWith(player) == 1 then
			dbg.stm("Player " .. player .. " lost " .. amount .. " unit(s) to the PT wall (min " .. Game.Time() .. ").")
		end
		ticksStati = 0
	end
end

-------------------------------------------------------------
-------------------------------------------------------------
------ generalUtility  --------------------------------------
-------Diese könnt ihr für eure Scripts nutzen---------------
-------------------------------------------------------------
function getTextForPlayerRace2(player)
    local raceId = Game.PlayerRace(player)

    if raceId == 0 then
        return "R"
    elseif raceId == 1 then
        return "W"
    elseif raceId == 2 then
        return "M"
    elseif raceId == 3 then
        return "D"
    elseif raceId == 4 then
        return "T"
    end
end

function destroySpectators()
	local player = 1
	while player <= 8 do
		if isIn(player, spectator) == 1 then
			destroyPlayer(player)
		end
		player = player + 1
	end
end

function destroyPlayer(player)
	local x = 0
	while x < mapsize do
		local y = 0
		while y < mapsize do
			if Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERSMALL,x,y,2*effectradius, Buildings.READY) > 0 then
				removePlayerBelongingsFromArea(player,x,y)
				return
			end
			y = y + effectradius
		end
		x = x + effectradius
	end
end

function removePlayerBelongingsFromArea(player, x, y)
	local counter = 1
	--IDs der Gebaeude gehen von 1 - 83
	while counter <= 83 do
		while Buildings.Amount(player, counter, Buildings.READY) > 0 do
			Buildings.Delete(Buildings.GetFirstBuilding(player, counter),2)
		end
		counter = counter +  1
	end
	counter = 1
	-- IDs der Sieder gehen von 1 - 80
	-- Swordsman, Bowman, Medics, Axewarriors, Blowgunwarriors, Backpackcatapulists: 29-43
	while counter <= 80 do
		Settlers.KillSelectableSettlers(player, counter, x, y, 64, 0)
		counter = counter +  1
	end
	counter = 1
	--IDs der Goods gehen von 1 - 43
	while counter <= 43 do
		Goods.Delete(x,y,64,counter)
		counter = counter +  1
	end
end

-- Berechnet die aktuellen verbrauchten Ressourcen des Spielers player und gibt sie zurück
function ressourcesBuilt(player)
    local res = 0
    local race = Game.PlayerRace(player)
    if race == 4 then race = 3 end
    race = race + 1

    local buildings = {
        1, 4, 3, 2, 40, 41, 42, 14, 17, 15, 16, 18, 20, 19, 21, 22, 11, 12, 9,
        10, 8, 6, 7, 5, 34, 33, 13, 32, 31, 44, 43, 64, 65, 66, 67, 68, 69, 70,
        71, 72, 73, 74, 75, 24, 46, 47, 45, 48, 23, 27
    }
    local buildingCost = {}
    buildingCost[1] = {
        4, 5, 7, 4, 6, 11, 22, 5, 5, 5, 6, 5, 10, 10, 8, 12, 12, 12, 6, 9, 8, 5,
        6, 6, 4, 4, 12, 6, 8, 17, 12, 6, 9, 6, 10, 8, 8, 6, 10, 7, 3, 9, 4, 9,
        5, 14, 4, 20, 11, 6
    }
    buildingCost[2] = {
        3, 4, 5, 2, 5, 12, 24, 5, 5, 5, 6, 5, 10, 10, 8, 12, 12, 12, 6, 8, 8, 5,
        6, 6, 4, 4, 12, 6, 8, 14, 10, 6, 4, 5, 5, 9, 4, 4, 7, 6, 7, 10, 8, 9, 5,
        13, 4, 20, 11, 6
    }
    buildingCost[3] = {
        4, 4, 7, 4, 5, 12, 24, 5, 5, 5, 6, 5, 10, 10, 8, 11, 12, 11, 6, 9, 8, 5,
        6, 6, 4, 4, 12, 5, 7, 14, 9, 3, 8, 10, 10, 7, 7, 9, 7, 9, 6, 7, 11, 9,
        5, 13, 4, 20, 10, 6
    }
    buildingCost[4] = {
        4, 4, 8, 4, 5, 9, 26, 6, 6, 6, 7, 6, 10, 4, 9, 14, 13, 13, 7, 10, 9, 5,
        6, 7, 4, 5, 13, 5, 7, 13, 8, 5, 8, 7, 8, 5, 5, 9, 8, 10, 9, 9, 11, 10,
        6, 16, 4, 23, 10, 4
    }

    local counter = 1
    while counter < 51 do
        res = res + buildingCost[race][counter] *
                  Buildings.Amount(player, buildings[counter], Buildings.READY)
        counter = counter + 1
    end

    if race == 1 then -- Roemer
        res = res + 10 *Buildings.Amount(player, Buildings.VINYARD, Buildings.READY)
        res = res + 6 *Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    elseif race == 2 then -- Wiki
        res = res + 6 *Buildings.Amount(player, Buildings.CHARCOALMAKER,Buildings.READY)
        res = res + 6 *Buildings.Amount(player, Buildings.BEEKEEPERHUT,Buildings.READY)
        res = res + 7 *Buildings.Amount(player, Buildings.MEADMAKERHUT,Buildings.READY)
    elseif race == 3 then -- Maya
        res = res + 6 *Buildings.Amount(player, Buildings.AGAVEFARMERHUT,Buildings.READY)
        res = res + 7 *Buildings.Amount(player, Buildings.TEQUILAMAKERHUT,Buildings.READY)
        res = res + 6*Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    elseif race == 4 then -- Trojaner
        res = res + 6*Buildings.Amount(player, Buildings.SUNFLOWERFARMERHUT,Buildings.READY)
        res = res + 6*Buildings.Amount(player, Buildings.SUNFLOWEROILMAKERHUT,Buildings.READY)
        res = res + 7*Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    end

    return res
end

```

<details>

<summary>Alte Version</summary>

```lua
-----------------------------------------------
-----------------------------------------------
--Script for Settlers IV 2v2 tournament 2022---
-----------------HAVE FUN ---------------------
-----------------------------------------------
-----------------------------------------------

-- diagonals [1 = wall, 0 = no wall] 
longdiagonal = 0
shortdiagonal = 1
towerradius = 33

effectradius = 8
mapsize = 1024

pt60units = {
	Settlers.PIONEER, Settlers.SABOTEUR, Settlers.PIONEER,
	Settlers.GARDENER, Settlers.SWORDSMAN_01, Settlers.SWORDSMAN_02,
	Settlers.SWORDSMAN_03, Settlers.BOWMAN_01, Settlers.BOWMAN_02,
	Settlers.BOWMAN_03, Settlers.AXEWARRIOR_01, Settlers.AXEWARRIOR_02,
	Settlers.AXEWARRIOR_03, Settlers.BLOWGUNWARRIOR_01,
	Settlers.BLOWGUNWARRIOR_02, Settlers.BLOWGUNWARRIOR_03,
	Settlers.BACKPACKCATAPULTIST_01, Settlers.BACKPACKCATAPULTIST_02,
	Settlers.BACKPACKCATAPULTIST_03, Settlers.MEDIC_01, Settlers.MEDIC_02,
	Settlers.MEDIC_03, Settlers.SQUADLEADER, Settlers.PRIEST
}

pt90units = {
	Settlers.SABOTEUR, Settlers.PIONEER
}

towers = {0,0,0,0}

function new_game()
    request_event(initGame, Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
	request_event(winCondition, Events.VICTORY_CONDITION_CHECK)
    request_event(ticking, Events.FIVE_TICKS)
end

function register_functions()
    reg_func(initGame)
    reg_func(winCondition)
    reg_func(ticking)
end

function winCondition()
    ---killSpecators
    Game.DefaultPlayerLostCheck(1)
	Game.DefaultPlayerLostCheck(2)
	Game.DefaultPlayerLostCheck(3)
	Game.DefaultPlayerLostCheck(4)
	local p = 1
	while p < 5 do
		if Game.HasPlayerLost(p) == 1 and Game.HasPlayerLost(getPartner(p)) == 1 then
			Game.PlayerLost(5)
			Game.PlayerLost(6)
			Game.PlayerLost(7)
			Game.PlayerLost(8)
		end
		p = p+1
	end
    Game.DefaultGameEndCheck()
end

--- Ein Debug schalter.
function isDebug()
	return 0;
end

function initGame()
	dbg.stm("Welcome to the Settlers IV 2v2 tournament 2022! Have fun!")
    if Game.LocalPlayer() >= 5 then Tutorial.RWM(1) end
	dbg.aioff(1)
	dbg.aioff(2)
	dbg.aioff(3)
	dbg.aioff(4)
	dbg.aioff(5)
	dbg.aioff(6)
	dbg.aioff(7)
	dbg.aioff(8)
end

ticksInit = 0
ticksPtWall = 0
ticksStati = 0
function ticking()
	ticksPtWall = ticksPtWall + 5
	ticksStati = ticksStati + 5
    if ticksPtWall >= 35 then
		ticksPtWall = 0
		ptWall()
	end
	if ticksStati >= 210 then
		ticksStati = 0
		if Game.LocalPlayer() >= 5 then
			dbg.stm("--------")
		end
		printMsgForPlayer(1)
        printMsgForPlayer(2)
		printMsgForPlayer(3)
		printMsgForPlayer(4)
	end
	if ticksInit < 30 then
		ticksInit = ticksInit + 5
	end
	if ticksInit == 30 then
		ticksInit = ticksInit + 5
		destroySpectators()
	end
end

function printMsgForPlayer(player)
	local AmountOfMilitary1 = Settlers.Amount(player, Settlers.SWORDSMAN_01)+
		Settlers.Amount(player, Settlers.BOWMAN_01)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_01)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_01)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_01)+
        Settlers.Amount(player, Settlers.MEDIC_01)

	local AmountOfMilitary2 = Settlers.Amount(player, Settlers.SWORDSMAN_02)+
		Settlers.Amount(player, Settlers.BOWMAN_02)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_02)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_02)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_02)+
        Settlers.Amount(player, Settlers.MEDIC_02)

    local AmountOfMilitary3 = Settlers.Amount(player, Settlers.SWORDSMAN_03)+
		Settlers.Amount(player, Settlers.BOWMAN_03)+
		Settlers.Amount(player,Settlers.AXEWARRIOR_03)+
        Settlers.Amount(player,Settlers.BLOWGUNWARRIOR_03)+
        Settlers.Amount(player,Settlers.BACKPACKCATAPULTIST_03)+
        Settlers.Amount(player, Settlers.MEDIC_03)+
        Settlers.Amount(player, Settlers.SQUADLEADER)

    local playerKills = Statistic.UnitsDestroyed(player)
    local playerSettlers = Settlers.Amount(player, Settlers.CARRIER)
    local playerOffenceFightingStrength = Game.GetOffenceFightingStrength(player)
    local playerMagic = Magic.CurrentManaAmount(player)
    local playerSABOTEUR = Settlers.Amount(player, Settlers.SABOTEUR)
    local playerTHIEF = Settlers.Amount(player, Settlers.THIEF)
    local playerResBuilt = ressourcesBuilt(player)
	
    if Game.LocalPlayer() >= 5 then
		dbg.stm("Min" .. Game.Time() .. " P" .. player .. " [" .. 
			getTextForPlayerRace2(player) .. "]: " .. (AmountOfMilitary1+AmountOfMilitary2+AmountOfMilitary3) .. " - " ..
            AmountOfMilitary1 .. "/ " .. AmountOfMilitary2 .. "/ " .. AmountOfMilitary3 .. " Soldiers | " .. playerKills .. " Kills | " ..
            playerSettlers .. " Settlers | " .. playerOffenceFightingStrength .. " KK | " ..
            playerMagic .. " Mana | " .. playerSABOTEUR .. " Sabos | " .. playerTHIEF .. " Thieves | " ..
            playerResBuilt .. " Res")
    end
end

warns = {0,0,0,0}
function ptWall()
	-- pt (1: 60, 2: 90, 3: >90)
	local pt
	if Game.Time() < 60 then
		pt = 1
	elseif Game.Time() < 90 then
		pt = 2
	else
		pt = 3
	end
	
	if pt < 3 then
		towers = {0, 0, 0, 0}
		if longdiagonal == 1 then
			WallCalcLong(pt)
		end
		if shortdiagonal == 1 then
			WallCalcShort(pt)
		end
		
		local index = 0
		while index < 4 do
			index = index + 1
			if towers[index] == 1 and warns[index] <= 15 then
				warns[index] = warns[index] + 1
				if (Game.LocalPlayer() == index or Game.LocalPlayer() == getPartner(index) or Game.LocalPlayer() >= 5) then 
					dbg.stm("Player " .. index .. " is building an illegal tower and will lose the match in " .. (30-2*warns[index]) .. " seconds!")
				end
				ticksStati = 0
			end
			if towers[index] == 0 and warns[index] > 0 then
				warns[index] = 0
				if (Game.LocalPlayer() == index or Game.LocalPlayer() == getPartner(index) or Game.LocalPlayer() >= 5) then 
					dbg.stm("Player " .. index .. " destroyed the illegal tower, situation defused (min " .. Game.Time() .. ").")
				end
				ticksStati = 0
			end
		end
		
		if warns[1] > 15 or warns[2] > 15 then
			Game.PlayerLost(1)
			Game.PlayerLost(2)
		end
		if warns[3] > 15 or warns[4] > 15 then
			Game.PlayerLost(3)
			Game.PlayerLost(4)
		end
	end
end

function WallCalcLong(pt)
	local x = effectradius
	local y = mapsize - effectradius
	while (x <= (mapsize - effectradius)) do
		WallCalcHelper(pt,x,y)
        x = x + effectradius
        y = y - effectradius
    end
end

function WallCalcShort(pt)
	local x = effectradius
	local y = effectradius
	while (x <= (mapsize - effectradius)) do
		WallCalcHelper(pt,x,y)
        x = x + effectradius
        y = y + effectradius
    end
end

function WallCalcHelper(pt,x,y)
	blocktowers(x,y)
	if (towers[1] == 1 or towers[2] == 1 or towers[3] == 1 or towers[4] == 1) then
		DrawEffects(x,y,Effects.MAGIC_PILE02,towerradius)
	end
	if pt == 2 then 
		removeUnitsNearPoint(x,y,effectradius,pt90units)
	elseif pt == 1 then 
		removeBoatsNearPoint(x,y,effectradius)
		removeUnitsNearPoint(x,y,effectradius,pt60units)
		DrawEffects(x,y,Effects.RMAGIC_JUPITERSLIGHTNING,effectradius)
	end
end

function DrawEffects(x,y,effect,radius)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y-radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x,y+radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x-radius,y-radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x-radius,y,7)
    --Effects.AddEffect(effect,Sounds.NO_SOUND,x-radius,y+radius,7)
    --Effects.AddEffect(effect,Sounds.NO_SOUND,x+radius,y-radius,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x+radius,y,7)
    Effects.AddEffect(effect,Sounds.NO_SOUND,x+radius,y+radius,7)
end

function blocktowers(x,y)
	local index = 0
	while index < 4 do 
		index = index + 1
		if Buildings.ExistsBuildingInArea(index,Buildings.GUARDTOWERSMALL,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0	or
				Buildings.ExistsBuildingInArea(index,Buildings.GUARDTOWERBIG,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0 or
				Buildings.ExistsBuildingInArea(index,Buildings.CASTLE,x,y,towerradius, Buildings.UNDERCONSTRUCTION) > 0 then
			towers[index] = 1
		end
	end
end
function removeBoatsNearPoint(x,y,radius)
    local ships = {Vehicles.WARSHIP, Vehicles.FERRY, Vehicles.WARMACHINE, Vehicles.CART}
    local index = 1
    while index <= getn(ships) do
        removeShipNearPoint(x,y,ships[index],radius,1)
		removeShipNearPoint(x,y,ships[index],radius,2)
        removeShipNearPoint(x,y,ships[index],radius,3)
        removeShipNearPoint(x,y,ships[index],radius,4)
        index = index + 1
    end
end

function removeShipNearPoint(x,y,ship,radius,player)
	if Vehicles.AmountInArea(player, ship, x, y, radius) > 0 then
		Vehicles.KillVehicles(player, ship, x, y, radius)
		if (Game.LocalPlayer() == player or Game.LocalPlayer() == getPartner(player) or Game.LocalPlayer() >= 5) then
			dbg.stm("Player " .. player .. " lost a vehicle to the PT wall (min " .. Game.Time() .. ")")
		end
		ticksStati = 0
    end
end

function removeUnitsNearPoint(x,y,radius,units)
    local index = 1
    while index <= getn(units) do
        removeUnitNearPoint(x,y,units[index],radius,1)
		removeUnitNearPoint(x,y,units[index],radius,2)
		removeUnitNearPoint(x,y,units[index],radius,3)
		removeUnitNearPoint(x,y,units[index],radius,4)
        index = index + 1
    end
end

function removeUnitNearPoint(x,y,unit,radius,player)
	local amount = Settlers.AmountInArea(player,unit,x,y,radius)
	if amount > 0 then
		Settlers.KillSelectableSettlers(player,unit,x,y,radius, 0)
		if (Game.LocalPlayer() == player or Game.LocalPlayer() == getPartner(player) or Game.LocalPlayer() >= 5) then
			dbg.stm("Player " .. player .. " lost " .. amount .. " unit(s) to the PT wall (min " .. Game.Time() .. ").")
		end
		ticksStati = 0
	end
end

-------------------------------------------------------------
-------------------------------------------------------------
------ generalUtility  --------------------------------------
-------Diese könnt ihr für eure Scripts nutzen---------------
-------------------------------------------------------------
function getTextForPlayerRace2(player)
    local raceId = Game.PlayerRace(player)

    if raceId == 0 then
        return "R"
    elseif raceId == 1 then
        return "W"
    elseif raceId == 2 then
        return "M"
    elseif raceId == 3 then
        return "D"
    elseif raceId == 4 then
        return "T"
    end
end

function getPartner(player)
	if longdiagonal == 1 and shortdiagonal == 1 then
		return player
	elseif longdiagonal == 1 and shortdiagonal == 0 then
		if (player == 2 or player == 4) then
			return player-1
		else
			return player+1
		end
	elseif longdiagonal == 0 and shortdiagonal == 1 then
		if (player == 1 or player == 2) then
			return player+2
		else
			return player-2
		end
	else
	
	end
end

function destroySpectators()
	destroyPlayer(5)
	destroyPlayer(6)
	destroyPlayer(7)
	destroyPlayer(8)
end

function destroyPlayer(player)
	local x = 0
	while x < mapsize do
		local y = 0
		while y < mapsize do
			if Buildings.ExistsBuildingInArea(player,Buildings.GUARDTOWERSMALL,x,y,2*effectradius, Buildings.READY) > 0 then
				removePlayerBelongingsFromArea(player,x,y)
				return
			end
			y = y + effectradius
		end
		x = x + effectradius
	end
end

function removePlayerBelongingsFromArea(player, x, y)
	local counter = 1
	--IDs der Gebaeude gehen von 1 - 83
	while counter <= 83 do
		while Buildings.Amount(player, counter, Buildings.READY) > 0 do
			Buildings.Delete(Buildings.GetFirstBuilding(player, counter),2)
		end
		counter = counter +  1
	end
	counter = 1
	-- IDs der Sieder gehen von 1 - 80
	-- Swordsman, Bowman, Medics, Axewarriors, Blowgunwarriors, Backpackcatapulists: 29-43
	while counter <= 80 do
		Settlers.KillSelectableSettlers(player, counter, x, y, 64, 0)
		counter = counter +  1
	end
	counter = 1
	--IDs der Goods gehen von 1 - 43
	while counter <= 43 do
		Goods.Delete(x,y,64,counter)
		counter = counter +  1
	end
end

-- Berechnet die aktuellen verbrauchten Ressourcen des Spielers player und gibt sie zurück
function ressourcesBuilt(player)
    local res = 0
    local race = Game.PlayerRace(player)
    if race == 4 then race = 3 end
    race = race + 1

    local buildings = {
        1, 4, 3, 2, 40, 41, 42, 14, 17, 15, 16, 18, 20, 19, 21, 22, 11, 12, 9,
        10, 8, 6, 7, 5, 34, 33, 13, 32, 31, 44, 43, 64, 65, 66, 67, 68, 69, 70,
        71, 72, 73, 74, 75, 24, 46, 47, 45, 48, 23, 27
    }
    local buildingCost = {}
    buildingCost[1] = {
        4, 5, 7, 4, 6, 11, 22, 5, 5, 5, 6, 5, 10, 10, 8, 12, 12, 12, 6, 9, 8, 5,
        6, 6, 4, 4, 12, 6, 8, 17, 12, 6, 9, 6, 10, 8, 8, 6, 10, 7, 3, 9, 4, 9,
        5, 14, 4, 20, 11, 6
    }
    buildingCost[2] = {
        3, 4, 5, 2, 5, 12, 24, 5, 5, 5, 6, 5, 10, 10, 8, 12, 12, 12, 6, 8, 8, 5,
        6, 6, 4, 4, 12, 6, 8, 14, 10, 6, 4, 5, 5, 9, 4, 4, 7, 6, 7, 10, 8, 9, 5,
        13, 4, 20, 11, 6
    }
    buildingCost[3] = {
        4, 4, 7, 4, 5, 12, 24, 5, 5, 5, 6, 5, 10, 10, 8, 11, 12, 11, 6, 9, 8, 5,
        6, 6, 4, 4, 12, 5, 7, 14, 9, 3, 8, 10, 10, 7, 7, 9, 7, 9, 6, 7, 11, 9,
        5, 13, 4, 20, 10, 6
    }
    buildingCost[4] = {
        4, 4, 8, 4, 5, 9, 26, 6, 6, 6, 7, 6, 10, 4, 9, 14, 13, 13, 7, 10, 9, 5,
        6, 7, 4, 5, 13, 5, 7, 13, 8, 5, 8, 7, 8, 5, 5, 9, 8, 10, 9, 9, 11, 10,
        6, 16, 4, 23, 10, 4
    }

    local counter = 1
    while counter < 51 do
        res = res + buildingCost[race][counter] *
                  Buildings.Amount(player, buildings[counter], Buildings.READY)
        counter = counter + 1
    end

    if race == 1 then -- Roemer
        res = res + 10 *Buildings.Amount(player, Buildings.VINYARD, Buildings.READY)
        res = res + 6 *Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    elseif race == 2 then -- Wiki
        res = res + 6 *Buildings.Amount(player, Buildings.CHARCOALMAKER,Buildings.READY)
        res = res + 6 *Buildings.Amount(player, Buildings.BEEKEEPERHUT,Buildings.READY)
        res = res + 7 *Buildings.Amount(player, Buildings.MEADMAKERHUT,Buildings.READY)
    elseif race == 3 then -- Maya
        res = res + 6 *Buildings.Amount(player, Buildings.AGAVEFARMERHUT,Buildings.READY)
        res = res + 7 *Buildings.Amount(player, Buildings.TEQUILAMAKERHUT,Buildings.READY)
        res = res + 6*Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    elseif race == 4 then -- Trojaner
        res = res + 6*Buildings.Amount(player, Buildings.SUNFLOWERFARMERHUT,Buildings.READY)
        res = res + 6*Buildings.Amount(player, Buildings.SUNFLOWEROILMAKERHUT,Buildings.READY)
        res = res + 7*Buildings.Amount(player, Buildings.AMMOMAKERHUT,Buildings.READY)
    end

    return res
end

```



</details>
