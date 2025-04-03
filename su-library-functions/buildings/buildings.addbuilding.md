---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.AddBuilding

## SU.Buildings.AddBuilding(x, y, playerID, buildingType)

Platziert ein Gebäude des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem Radius von 4 Feldern nach einer freien Stelle gesucht, an der das Gebäude platziert werden kann.

⇒ Radius: siehe [buildings.addbuilding-1.md](buildings.addbuilding-1.md "mention")

Diese Funktion behebt das Fehlverhalten der originalen S4-Funktion `Buildings.AddBuilding(...)`, die dieses Verhalten eigentlich haben sollte.

#### Notiz

* diese Funktion prüft z.Z. **nicht**, ob Siedler im Weg stehen. **D.h., wird ein Gebäude mit dieser Funktion an einer Stelle platziert, an der Siedler stehen, stürzt das Spiel ab**, da die Siedler im Gebäude gefangen werden und feststecke&#x6E;**!** Eine Lösung ist in Arbeit...\
  ⇒ D.h. **diese Funktion** sollte **nur ganz zu Beginn des Spieles verwendet** werden, wenn noch keine/kaum Siedler in der Map verteilt sind!\
  ⇒ **Der sicherste Weg** ist es, statt Gebäuden **Baustellen zu platzieren**. Diese können nämlich auch über Siedler gesetzt werden kann (siehe [buildings.addbuilding-2.md](buildings.addbuilding-2.md "mention")).

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")

#### Rückgabewert

* Gebäude-ID
* 0: Fehler, z.B. wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

<pre class="language-lua"><code class="lang-lua"><strong>local buildingID = SU.Buildings.AddBuildingSU(100, 100, 1, Buildings.GUARDTOWERSMALL)
</strong></code></pre>
