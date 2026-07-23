# Buildings.Delete

## `Buildings.Delete(ID, Löschtyp)`

Löscht ein Gebäude. Anders als bei CrushBuilding kann die Erstattung der Rohstoffe verhindert werden. Siedler überleben.

<table><thead><tr><th width="252.57142857142856">Löschtyp</th><th>Beschreibung</th></tr></thead><tbody><tr><td>0</td><td>Stehen lassen</td></tr><tr><td>1</td><td>Abreißen (wie <a data-mention href="buildings.crushbuilding.md">buildings.crushbuilding.md</a>, 50% Ressourcen)</td></tr><tr><td>2</td><td>Zerstören (<strong>keine</strong> Ressourcen)</td></tr></tbody></table>

Werte darüber verhalten sich wie 0.

#### Rückgabewert

Anzahl der Gebäude

#### Beispiel

```lua
Buildings.Delete(Buildings.GetFirstBuilding(4, Buildings.GUARDTOWERSMALL), 2)  --//Ermittelt den kleinen Turm des zweiten Spielers mit der kleinsten ID und zerstört ihn, es wird kein Material erstattet.
Buildings.Delete(Buildings.AddBuilding(150,75,1,Buildings.GUARDTOWERBIG), 1)  --//Plat
```
