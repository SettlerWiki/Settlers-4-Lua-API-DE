---
description: by MuffinMario
---

# Ground-Library

{% embed url="https://github.com/MuffinMario/Siedler-IV-Lua-Ground-Library" %}

Kleine Library für Böden setzen. Echt klein Einfach inhalt in deine Map copy-pasten und du kannst die Methode

`Grounds.SetGround(x,y,radius,groundID)`

benutzen

<details>

<summary>groundlibrary.lua</summary>

{% code title="groundlibrary.lua" %}
```lua
--Nötige Information!!!
-- - BodenID Grounds.GLITCHED ist eine kollektive Sammlung von Böden gemischt mit lila und schwarzen Texturen
-- - War der Boden vorher Meer (z.b. Level 5) Werden Wassertiere auf dem Boden dennoch zufällig erscheinen.
-- - War der Boden vorher Meer werden Einheiten einen Befehl zwar wahrnehmen können, hängen aber fest, wenn sie die Position erreichen. 
--	Manchmal passiert das auch nicht. Um das zu beheben immer erst auf Fluss Boden (z.b. id 96) setzen und dann auf den gewünschten boden.
-- - Strand verbindet sich normalerweise mit dem Meer, aber damit die "verbindung" entstehen kann benötigt der Strand Wasser Level 1
-- 	(kein anderes Level)
-- - Alle anderen BodenIDs sind unbaubares Grass, kann man auch zum Vorteil einsetzen!
$ifnot GROUNDS_LIBRARY100_MM
--zeile bitte ignorieren/ignore this line
GROUNDS_LIBRARY100_MM= ""

Grounds = {


	
	--0x0X
	WATER1 = 0,
	WATER2 = 1,
	WATER3 = 2,
	WATER4 = 3,
	WATER5 = 4,
	WATER6 = 5,
	WATER7 = 6,
	WATER8 = 7,
	
	--0x1X
	GRASS = 16 + 0,
	GRASS_MOUNTAIN  = 16 + 1,
	GRASS_ISLAND = 16 + 2,
	GRASS_DESERT = 16 + 4,
	GRASS_SWAMP = 16 + 5,
	GRASS_MUD = 16 + 7,
	GRASS_DARK = 16 + 8,
	GRASS_WEIRD = 16 + 9,
	GRASS_DUSTY = 16 + 12,
	GRASS_PAVEMENT = 16 + 13,

	-- 0x2X
	MOUNTAIN = 32 + 0,
	MOUNTAIN_GRASS = 32 + 1,
	MOUNTAIN_SNOW = 32 + 3,

	-- 0x3X
	SAND = 48 + 0,

	-- 0x4X
	DESERT = 64 + 0,
	DESERT_GRASS = 64 + 1,

	-- 0x5X
	SWAMP = 80 + 0,
	SWAMP_GRASS = 80 + 1,

	-- 0x6X
	RIVER1 = 96 + 0,
	RIVER2 = 96 + 1,
	RIVER3 = 96 + 2,
	RIVER4 = 96 + 3,
	
	-- 0x7X ???
	UNIDENTIFIED_GRASS1 = 112 + 0, -- komisches Grass ohne verbindungen zu anderen böden (unbaubar natürlich)
	UNIDENTIFIED_GRASS2 = 112 + 1, -- komisches Grass ohne verbindungen zu anderen böden (unbaubar natürlich)
	UNIDENTIFIED_GRASS3 = 112 + 2, -- komisches Grass ohne verbindungen zu anderen böden (unbaubar natürlich)

	-- 0x8X
	SNOW = 128 + 0,
	SNOW_MOUNTAIN = 128 + 1,
	
	-- extra stuff
	GLITCHED = 250

}
-- @param x X-Koordinate
-- @param y Y-Koordinate
-- @param radius Radius (0 ist nicht leer)
-- @param groundID ID des Bodens
function Grounds.SetGround(x,y,radius,groundID)
	return dbg.sg(x,y,radius,groundID) -- ret nil
end
$end
```
{% endcode %}

</details>

```lua
-- Vergewissere dich, dass vor diesem Code noch die Library in das Script gehört!

function new_game()
  -- Setze auf Position X 100 Y 200 einen Punkt Gras
  Grounds.SetGround(100,200,0,Grounds.GRASS) 
  -- Setze auf Position X 100 X 100 einen Bereich von r = 3 punkten mit Wüste. Aussen sollte überall Gras sein.
  Grounds.SetGround(100,100,5,Grounds.GRASS_DESERT) -- GRASS-WÜSTE
  Grounds.SetGround(100,100,4,Grounds.DESERT_GRASS) -- WÜSTE-GRASS
  Grounds.SetGround(100,100,3,Grounds.DESERT) -- WÜSTE
end
```
