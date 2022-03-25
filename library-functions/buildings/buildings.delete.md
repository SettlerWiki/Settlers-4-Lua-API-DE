# Buildings.Delete

## `Buildings.Delete(ID, Löschtyp)`

Löscht ein Gebäude. Anders als bei CrushBuilding kann die Erstattung der Rohstoffe verhindert werden, aber etwaige Siedler überleben. Löschtypen scheinen zu sein:&#x20;

|   |                                 |
| - | ------------------------------- |
| 0 | Stehen lassen                   |
| 1 | Abreißen   (wie CrushBuilding)  |
| 2 | Zerstören                       |

Werte darüber verhalten sich wie eine 0.

#### Rückgabewert

Anzahl der Gebäude

#### Beispiel

```lua
Buildings.Delete(Buildings.GetFirstBuilding(4, Buildings.GUARDTOWERSMALL), 2)  --//Ermittelt den kleinen Turm des zweiten Spielers mit der kleinsten ID und zerstört ihn, es wird kein Material erstattet.
Buildings.Delete(Buildings.AddBuilding(150,75,1,Buildings.GUARDTOWERBIG), 1)  --//Plat
```
