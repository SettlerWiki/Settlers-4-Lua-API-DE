# Mehr als 8 Waren spawnen

Mit der Funktion [Goods.AddPileEx() ](../../library-functions/goods/goods.addpileex.md)könnt ihr einen Warenstapel setzen. Wenn ihr jedach bei der Anzahl der Güter einen höheren Wert als 8 eintragt, führt dies zu einem FE. Daher benötigt ihr einen kleinen Workarround:

```lua
function addSupplies(X, Y, goodtype, amount)
	local i = 0
	while i < amount do
		if (amount-i) < 8 then
			Goods.AddPileEx(X, Y, goodtype, (amount-i))
			i = i + amount
		else
			Goods.AddPileEx(X, Y, goodtype, 8)
			i = i + 8
		end
	end
end
```

Hier wird bei einem höheren Anzahl als 8 die Waren gesplittet auf mehrere Stapel, wodurch es zu keinem FE mehr kommt.&#x20;
