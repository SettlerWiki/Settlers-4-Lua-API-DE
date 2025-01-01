---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Buildings.AddBuildingSU

## `Buildings.AddBuildingSU(x, y, Spieler, Gebäude)`

Platziert ein Gebäude des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem Radius von 4 Feldern nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

⇒ Radius: siehe [buildings.addbuilding-2.md](buildings.addbuilding-2.md "mention")

Diese Funktion behebt das Fehlverhalten der originalen S4-Funktion `Buildings.AddBuilding(...)`, die dieses Verhalten eigentlich haben sollte.

#### Rückgabewert

Eindeutige Gebäude-ID oder 0, wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

<pre class="language-lua"><code class="lang-lua"><strong>local buildingID = Buildings.AddBuildingSU(100,100, 1, Buildings.GUARDTOWERSMALL)
</strong></code></pre>
