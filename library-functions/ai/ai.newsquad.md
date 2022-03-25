# AI.NewSquad

## `AI.NewSquad(Partei, Befehl, X, Y)`

Erteilt allen Einheiten, die per Script erstellt wurden und noch keinen Befehl erhalten haben, einen Befehl. Jede Einheit kann nur einmal angesprochen werden. Mögliche Befehle sind:

|                           |                                                               |
| ------------------------- | ------------------------------------------------------------- |
| AI.CMD\_MOVE\_AND\_STAY   | Einheit bleibt am Zielort                                     |
| AI.CMD\_MOVE\_AND\_VANISH | Einheit verschwindet am Zielort                               |
| AI.CMD\_MOVE\_HOME        | Einheit bewegt sich zur Siedlung, erfordert keine Koordinaten |
| AI.CMD\_SUICIDE\_MISSION  | Einheit greift an, erfordert keine Koordinaten                |

Einheiten reagieren nur auf Befehle, wenn bei ihrer Erstellung der Parameter "zum Squad hinzufügen" auf 1 gestellt ist, z.B. bei Schiffen Sonst kann es passieren, dass die Einheiten erscheinen, aber nichts tun.

#### Rückgabewert

none

#### Beispiel

```lua
--gesamtes Beispiel
Vehicles.AddVehicle(100,200,2,Vehicles.FERRY,0,0,1) -- schiff wird durch NewSquad Befehl bewegt
Vehicles.AddVehicle(140,200,2,Vehicles.FERRY,0,0,0) -- schiff wird nicht bewegt (letzter parameter = 0)
AI.NewSquad(2, AI.CMD_MOVE_AND_STAY, 144, 340) -- das schiff auf X100 Y200 bewegt sich nun auf X144 Y340 zu


--mögliche implementierungen:
AI.NewSquad(2, AI.CMD_SUICIDE_MISSION )
AI.NewSquad(2, AI.CMD_MOVE_AND_STAY, 144, 340)
AI.NewSquad(2, AI.CMD_MOVE_HOME)
AI.NewSquad(2, AI.CMD_MOVE_AND_VANISH, 884, 11)
```

