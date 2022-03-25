# Platzieren von Gebäuden

Im folgenden schauen wir wie man möglichst effektiv Gebäude setzten kann ohne jedes Gebäude selbst per Hand einzutippen. Wir reduzieren den Prozess auf ein Minimum indem nur noch die entsprechenden Koordinaten in ein Array einzutragen sind und per Funktion gesetzt werden. Zuerst legen wir ein Array an:

<details>

<summary>Buildings Array</summary>

```lua
buildings={

						{},                                              --WOODCUTTERHUT1

						{},                                              --FORESTERHUT2

						{},                                              --SAWMILL 3

						{},                                              --STONECUTTERHUT4

						{},                                              --WATERWORKHUT5

						{},                                    		 --FISHERHUT6

						{},                                              --HUNTERHUT7

						{},                                              --SLAUGHTERHOUSE8

						{},                                              --MILL9

						{},                                              --BAKERY10

						{},                                              --GRAINFARM11

						{},                                              --ANIMALRANCH12

						{},                                              --DONKEYRANCH13

						{},                                              --STONEMINE14

						{},                                              --IRONMINE15

						{},                                              --GOLDMINE16

						{},                                              --COALMINE17

						{},                                              --SULFURMINE18

						{},                                              --SMELTGOLD19

						{},                                              --SMELTIRON20

						{},                                              --TOOLSMITH21

						{},                                              --WEAPONSMITH22

						{},                                              --VEHICLEHALL23

						{},                                              --BARRACKS24

						{},                                              --CHARCOALMAKER25

						{},                                              --TRAININGCENTER26

						{},                                              --HEALERHUT27

						{},                                              --AMMOMAKERHUT28

						{},                                              --GUNPOWDERMAKERHUT29

						{},                                              --LANDSCAPEMAKERHUT30

						{},                                              --SHIPYARD31

						{},                                              --PORT32

						{},                                              --MARKETPLACE33

						{},                                              --STORAGEAREA34

						{},                                              --VINYARD,35

						{},                                              --AGAVEFARMERHUT36

						{},                                              --TEQUILAMAKERHUT37

						{},                                              --BEEKEEPERHUT38

						{},                                              --MEADMAKERHUT39

						{},                                              --RESIDENCESMALL40

						{},                                              --RESIDENCEMEDIUM41

						{},                                              --RESIDENCEBIG42

						{},                                              --SMALLTEMPLE43

						{},                                              --BIGTEMPLE44

						{},                                              --LOOKOUTTOWER45

						{{350,300},{380,293},{410,307},{350,270},        --GUARDTOWERSMALL46

						 {350,240}},                                     --      "

						{},                                              --GUARDTOWERBIG47

						{},                                              --CASTLE48

						{},                                              --MUSHROOMFARM49

						{},                                              --DARKTEMPLE50

						{},                                              --FORTRESS51

						{},                                              --PORTA52

						{},                                              --PORTB53

						{},                                              --PORTC54

						{},                                              --PORTD55

						{},                                              --PORTE56

						{},                                              --PORTF57

						{},                                              --SHIPYARDA58

						{},                                              --SHIPYARDB59

						{},                                              --SHIPYARDC60

						{},                                              --SHIPYARDD61

						{},                                              --SHIPYARDE62

						{},                                              --SHIPYARDF63

						{},                                              --EYECATCHER0164

						{{350,290}},                                     --EYECATCHER0265

						{{350,285}},                                     --EYECATCHER0367

						{{350,280}},                                     --EYECATCHER0468

						{{355,300}},                                     --EYECATCHER0569

						{},                                              --EYECATCHER0670

						{},                                              --EYECATCHER0771

						{},                                              --EYECATCHER0872

						{},                                              --EYECATCHER0973

						{},                                              --EYECATCHER1074

						{},                                              --EYECATCHER1175

						{},                                              --EYECATCHER1276

						{},                                              --SHIPYARDG77

						{},                                              --SHIPYARDH78

						{},                                              --PORTG79

						{},                                              --PORTH80

						{},                                              --MANACOPTERHALL81

						{},                                              --SUNFLOWEROILMAKERHUT82

						{}                                               --SUNFLOWERFARMERHUT83

				}
```

</details>

In dem Array werden beispielshalber einige kleine Türme gesetzt und ein paar Zierobjekte. Möchte man also ein Gebäude an einer Stelle hinzufügen trägt man sie an die richtige Stelle mit Koordinaten in das Arrays ein.

Damit aus dem Array auch die entsprechenden Gebäude gebaut werden brauchen wir noch eine Funktion. Diese sieht so aus:

```lua
function placebuildings(partei)
	--placement of new foundation buildings
	_type=46
	while _type<49 do
		_number=1
		while buildings[_type][_number]~=nil do
			Buildings.AddBuildingEx((buildings[_type][_number][1]),(buildings[_type][_number][2]),partei,_type)
			_number=_number+1
		end
		_type=_type+1
	end
 
	--placement of new non-foundation buildings
	_type=1
	while _type<83 do
		_number=1
		while buildings[_type][_number]~=nil do
			Buildings.AddBuildingEx((buildings[_type][_number][1]),(buildings[_type][_number][2]),partei,_type)
			_number=_number+1
		end
		if _type==45 then
			_type=49
		else
			_type=_type+1
		end
	end
end
```

Die Funktion läuft über das Array und setzt zuerst die Grundgebäude und danach die restlichen Gebäude in Reihenfolge ihrer Nummer.\
\
Die Funktion wird mit dem Parameter der entsprechenden Partei wie folgt aufgerufen:

`placebuildings(1)`&#x20;

Ausnahmen unter den Gebäuden ist Nummer 32 PORT Nummer 36 SHIPYARD, Nummer 30 LANDSCAPEMAKERHUT und Nummer 26 TRAININGSCENTER. Diese können nicht gesetzt werden da sie im aktuellen Spiel nicht mehr existieren.\
\
Abschließend sei gesagt, dass das Spiel abstürzt falls Gebäude in Wasser und außerhalb der Grenzen gesetzt werden. Will man ein Gebäude bauen welches nicht dem passenden Volk entspricht kommt es ebenfalls zum Fatal Error. Auch konnten wir beobachten, das ein Platzieren der Gebäude bei bestimmten Siedlertypen (u.a. Esel) zu abstürzen führen kann. \
**Ihr müsst also das platzieren von Gebäuden immer ausreichend testen, da es unter umständen zu FEs kommen kann!**
