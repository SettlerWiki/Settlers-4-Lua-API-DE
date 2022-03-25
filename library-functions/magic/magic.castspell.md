# Magic.CastSpell

## `Magic.CastSpell(Spieler, Volk, Zauber, x, y,)`

Bewirkt den angegebenen Zauber an der angegebenen Stelle durch den angegebenen Spieler. Der Spieler darf noch nicht besiegt worden sein. Mit Volk ist die Nummer gemeint - 0 für Römer, 1 für Wikinger, 2 für Maya, 3 für das Dunkle Volk, 4 für Trojaner. Negative Werte führen dazu, dass die Standardzauber des Volkes genutzt werden. Auf diese Weise können sogar Zauber von Völkern genutzt werden, die auf der Karte nicht anwesend sind. Zauber werden entweder durch die Zahlen 0-7 (basierend auf ihrer Reihenfolge im Menü) oder durch ihren internen Namen ausgewählt:

|                        |   |
| ---------------------- | - |
| SPELL\_DIVINE\_PRESENT | 0 |
| SPELL\_CONVERT\_GOOD   | 1 |
| SPELL\_FOOD            | 2 |
| SPELL\_TERRAIN         | 3 |
| SPELL\_DEFENSE         | 4 |
| SPELL\_ATTACK          | 5 |
| SPELL\_SOLDIER         | 6 |
| SPELL\_SPECIAL         | 7 |

#### Rückgabewert

none

#### Beispiel

```lua
Magic.CastSpell(1,-1,3,438,481) --//Abkürzungszauber (außer Spieler 1 spielt als Dunkles Volk)
Magic.CastSpell(4,-1,Magic.SPELL_CONVERT_GOOD, 374, 261) --//Güterumwandlung
Magic.CastSpell(1,4,7,100,100) --//Orakel von Delphi auf den Koordinaten 100/100 (unabhängig vom Spielervolk)
Magic.CastSpell(1,4,Magic.SPELL_SPECIAL,100,100) --//Das gleiche wie oben, nur mit dem Zaubernamen statt der Zahl.
```
