---
description: by kdsystem1337 public shared on Muffinmarios Discord
---

# Turnier Map Script 2vs2

```lua
spectator = { 5,6,7,8 }

function newOrLoadedGame()
    Vars.Save1 = 0
    Vars.Save2 = 0

    local i,v = next(spectator,nil)
    local localPlayer = Game.LocalPlayer();
    while i do
        if localPlayer == v then
            Tutorial.RWM(1);
        end
        i,v = next(spectator,i);
    end

    dbg.stm("The Settlers IV Tournament Summer 2020 Map 43")
    dbg.stm("PeaceTime: 60 Min. Thieves are allowed from 0 minutes and may steal from 60 minutes and Sabotours are allowed from 90 minutes")

    if Game.LocalPlayer() >= 5 then
                dbg.stm("Scriptversion 1.2")
    end
    --Buildings.Delete(Buildings.GetFirstBuilding(5, 46),2)
    --Buildings.Delete(Buildings.GetFirstBuilding(6, 46),2)
    --Buildings.Delete(Buildings.GetFirstBuilding(7, 46),2)
    --Buildings.Delete(Buildings.GetFirstBuilding(8, 46),2)
end

function new_game()
    request_event(Info, Events.FIVE_TICKS);
    request_event(newOrLoadedGame,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME);
end

function register_functions()
    reg_func(newMinute);
    reg_func(minuteReached);
    reg_func(Info);
    reg_func(newOrLoadedGame);
    MinuteEvents.register_functions();
end


function minuteReached(value)
    if Game.Time() == value then
        if Vars.Save2 ~= value then
            Vars.Save2 = value
            return 1
        else
            return 0
        end
    end
end

function newMinute()
    if Vars.Save1 ~= Game.Time() then
        Vars.Save1 = Game.Time()
        return 1
    else 
        return 0
    end
end

function Info()
    if newMinute() == 1 then
        playerId = 1
        Player1AmountOfMilitary =  Settlers.Amount(playerId, Settlers.SWORDSMAN_01) +  Settlers.Amount(playerId, Settlers.SWORDSMAN_02) + Settlers.Amount(playerId, Settlers.SWORDSMAN_03) + Settlers.Amount(playerId, Settlers.BOWMAN_01) +  Settlers.Amount(playerId, Settlers.BOWMAN_02) + Settlers.Amount(playerId, Settlers.BOWMAN_03)+ Settlers.Amount(playerId, Settlers.AXEWARRIOR_01) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_02) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_01) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_02) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03) +Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_01)	+ Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_02) + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_01) + Settlers.Amount(playerId, Settlers.MEDIC_02) + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER)
        Player1AmountOfMilitary3 =  Settlers.Amount(playerId, Settlers.SWORDSMAN_03) +  Settlers.Amount(playerId, Settlers.BOWMAN_03) +Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03)  + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER) 
        Player1Kills= Statistic.UnitsDestroyed(playerId)
        Player1Settlers = Settlers.Amount(playerId, Settlers.CARRIER)
		Player1OffenceFightingStrength = Game.GetOffenceFightingStrength(playerId)
		Player1Magic = Magic.CurrentManaAmount(playerId)
		Player1SABOTEUR = Settlers.Amount(playerId,Settlers.SABOTEUR)
		Player1THIEF = Settlers.Amount(playerId,Settlers.THIEF)
		
        playerId = 2
        Player2AmountOfMilitary =  Settlers.Amount(playerId, Settlers.SWORDSMAN_01) +  Settlers.Amount(playerId, Settlers.SWORDSMAN_02) + Settlers.Amount(playerId, Settlers.SWORDSMAN_03) + Settlers.Amount(playerId, Settlers.BOWMAN_01) +  Settlers.Amount(playerId, Settlers.BOWMAN_02) + Settlers.Amount(playerId, Settlers.BOWMAN_03)+ Settlers.Amount(playerId, Settlers.AXEWARRIOR_01) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_02) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_01) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_02) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03) +Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_01)	+ Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_02) + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_01) + Settlers.Amount(playerId, Settlers.MEDIC_02) + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER)
        Player2AmountOfMilitary3 =  Settlers.Amount(playerId, Settlers.SWORDSMAN_03) +  Settlers.Amount(playerId, Settlers.BOWMAN_03) +Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03)  + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER)      	 
        Player2Kills= Statistic.UnitsDestroyed(playerId)
        Player2Settlers = Settlers.Amount(playerId, Settlers.CARRIER)
		Player2OffenceFightingStrength = Game.GetOffenceFightingStrength(playerId)
		Player2Magic = Magic.CurrentManaAmount(playerId)
		Player2SABOTEUR = Settlers.Amount(playerId,Settlers.SABOTEUR)
		Player2THIEF = Settlers.Amount(playerId,Settlers.THIEF)

        playerId = 3
        Player3AmountOfMilitary =  Settlers.Amount(playerId, Settlers.SWORDSMAN_01) +  Settlers.Amount(playerId, Settlers.SWORDSMAN_02) + Settlers.Amount(playerId, Settlers.SWORDSMAN_03) + Settlers.Amount(playerId, Settlers.BOWMAN_01) +  Settlers.Amount(playerId, Settlers.BOWMAN_02) + Settlers.Amount(playerId, Settlers.BOWMAN_03)+ Settlers.Amount(playerId, Settlers.AXEWARRIOR_01) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_02) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_01) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_02) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03) +Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_01)	+ Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_02) + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_01) + Settlers.Amount(playerId, Settlers.MEDIC_02) + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER)
        Player3AmountOfMilitary3 =  Settlers.Amount(playerId, Settlers.SWORDSMAN_03) +  Settlers.Amount(playerId, Settlers.BOWMAN_03) +Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03)  + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER) 
        Player3Kills= Statistic.UnitsDestroyed(playerId)
        Player3Settlers = Settlers.Amount(playerId, Settlers.CARRIER)
		Player3OffenceFightingStrength = Game.GetOffenceFightingStrength(playerId)
		Player3Magic = Magic.CurrentManaAmount(playerId)
		Player3SABOTEUR = Settlers.Amount(playerId,Settlers.SABOTEUR)
		Player3THIEF = Settlers.Amount(playerId,Settlers.THIEF)

        playerId = 4
        Player4AmountOfMilitary =  Settlers.Amount(playerId, Settlers.SWORDSMAN_01) +  Settlers.Amount(playerId, Settlers.SWORDSMAN_02) + Settlers.Amount(playerId, Settlers.SWORDSMAN_03) + Settlers.Amount(playerId, Settlers.BOWMAN_01) +  Settlers.Amount(playerId, Settlers.BOWMAN_02) + Settlers.Amount(playerId, Settlers.BOWMAN_03)+ Settlers.Amount(playerId, Settlers.AXEWARRIOR_01) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_02) + Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_01) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_02) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03) +Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_01)	+ Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_02) + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_01) + Settlers.Amount(playerId, Settlers.MEDIC_02) + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER)
        Player4AmountOfMilitary3 =  Settlers.Amount(playerId, Settlers.SWORDSMAN_03) +  Settlers.Amount(playerId, Settlers.BOWMAN_03) +Settlers.Amount(playerId, Settlers.AXEWARRIOR_03) + Settlers.Amount(playerId, Settlers.BLOWGUNWARRIORS_03)  + Settlers.Amount(playerId, Settlers.BACKPACKCATAPULIST_03)  + Settlers.Amount(playerId, Settlers.MEDIC_03) + Settlers.Amount(playerId, Settlers.SQUADLEADER) 
        Player4Kills= Statistic.UnitsDestroyed(playerId)
        Player4Settlers = Settlers.Amount(playerId, Settlers.CARRIER) 
		Player4OffenceFightingStrength = Game.GetOffenceFightingStrength(playerId)
		Player4Magic = Magic.CurrentManaAmount(playerId)
		Player4SABOTEUR = Settlers.Amount(playerId,Settlers.SABOTEUR)
		Player4THIEF = Settlers.Amount(playerId,Settlers.THIEF)
		
        if Game.LocalPlayer() >= 5 then
	     dbg.stm("Statistics for minute "..Game.Time())
	     dbg.stm("P1: " .. Player1AmountOfMilitary.. " Soldiers # " .. Player1AmountOfMilitary3 .." L3 # " .. Player1OffenceFightingStrength .. "KK # " .. Player1Kills .. " Kills # " .. Player1Magic .." Magic # " .. Player1SABOTEUR .." Sabos # " .. Player1THIEF .." Thieves # " .. Player1Settlers .. " Settlers")
	     dbg.stm("P2: " .. Player2AmountOfMilitary.. " Soldiers # " .. Player2AmountOfMilitary3 .." L3 # " .. Player2OffenceFightingStrength .. "KK # " .. Player2Kills .. " Kills # " .. Player2Magic .." Magic # " .. Player2SABOTEUR .." Sabos # " .. Player2THIEF .." Thieves # " .. Player2Settlers .. " Settlers")
	     dbg.stm("P3: " .. Player3AmountOfMilitary.. " Soldiers # " .. Player3AmountOfMilitary3 .." L3 # " .. Player3OffenceFightingStrength .. "KK # " .. Player3Kills .. " Kills # " .. Player3Magic .." Magic # " .. Player3SABOTEUR .." Sabos # " .. Player3THIEF .." Thieves # " .. Player3Settlers .. " Settlers")
	     dbg.stm("P4: " .. Player4AmountOfMilitary.. " Soldiers # " .. Player4AmountOfMilitary3 .." L3 # " .. Player4OffenceFightingStrength .. "KK # " .. Player4Kills .. " Kills # " .. Player4Magic .." Magic # " .. Player4SABOTEUR .." Sabos # " .. Player4THIEF .." Thieves # " .. Player4Settlers .. " Settlers")
        end

    end
    if minuteReached(60) == 1 then
        dbg.stm("--------------------")
        dbg.stm("Let the battle begin! PeaceTime (PT) is over!")
        dbg.stm("--------------------")
    end
end
```
