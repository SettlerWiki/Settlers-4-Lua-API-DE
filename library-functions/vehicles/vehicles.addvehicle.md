# Vehicles.AddVehicle

## `Vehicles.AddVehicle(x, y, Spieler, Fahrzeugtyp, Richtung, Munition, Commands)`

Fügt eines der folgenden Fahrzeuge hinzu:&#x20;

* Vehicles.WARSHIP
* Vehicles.FERRY
* Vehicles.TRANSPORTSHIP
* Vehicles.WARMACHINE
* Vehicles.FOUNDATION\_CART&#x20;

Wenn nicht alle Parameter ausgefüllt werden, wird die Einheit nicht auf Befehle wie AI.NewSquad() reagieren. Munition gilt nur für Kriegsschiffe und Kriegsmaschinen, auf alle anderen Einheiten hat der Wert keine Wirkung. Die Richtung wird als Zahl angegeben. Commands entscheidet, ob das Fahrzeug auf Bewegungsbefehle durch das Script reagieren wird (1 für ja, 0 für nein).

#### Rückgabewert

none

#### Beispiel

```lua
Vehicles.AddVehicle(144, 340, 1, Vehicles.WARSHIP, 1, 100, 0)  --//Dieses Schiff wird nicht auf Bewegungsbefehle durch das Script reagieren.
Vehicles.AddVehicle(153, 313, 1, Vehicles.FERRY, 1, 0, 1) --//Dieses Schiff wird auf Bewegungsbefehle reagieren.
```
