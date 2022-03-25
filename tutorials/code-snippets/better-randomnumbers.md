---
description: by Hippo
---

# Verbesserte Zufallszahlen

{% hint style="info" %}
Ihr müsst **randomNumber** durch eine [Vars.Save-Variable](../advanced-tipps/die-vars.save-variablen.md) ersetzen, wenn der Zufall nicht nur zu Spielstart gebraucht wird, sondern auch später während des Spiels
{% endhint %}

```lua
randomNumber = 0

function new_game()
    initializeRandom()
end

-- returns an integer between a and b. b must be greater then a
function getRandomBetween(a, b)
	if b < a then
		return false
	end
	return getRandomNumber(b-a) + a
end

-- returns an integer between 0 and maxRandom-1
function getRandomNumber(maxRandom)
    -- randomNumber will be set to a new “random” number in [0,1) using the Monte-Carlo-Algorithm
    randomNumber = randomNumber*pow(5,13)/pow(10,8)
    randomNumber = tonumber(strsub("" .. randomNumber, strfind("" .. randomNumber, "(%.+)"))) -- drop everything before .
    local nextRandom = randomNumber * maxRandom -- nextRandom is in [0,maxRandom)
    return tonumber(strsub("" .. nextRandom, 1, strfind("" .. nextRandom, "(%.+)"))) -- drop everything after .
end

-- does not really get the exact number of hours since 1970. But the exact number doesn’t matter. It will give a different number every hour at least which then can be used as the first seed for the random number generator
function getHour()
    local year = tonumber(date("%Y")) - 1970
    local month = tonumber(date("%m")) + year*12
    local day = tonumber(date("%d")) + month*30
    local hour = tonumber(date("%H")) + day*24
    -- local minute = tonumber(date("%M")) + hour*60
    -- local second = tonumber(date("%S")) + minute*60
    
    return hour
end

-- returns base^exponent
-- rounds the exponent down to the next integer
-- will return 1 if exponent<1, so also ignoring negative numbers (we don’t need them here)
function pow(base, exponent)
    local expNr = 0
    local toReturn = 1
    while expNr < exponent
    do
        toReturn = toReturn * base
        expNr = expNr + 1
    end
    return toReturn
end


-- gets the seed and then 100000 random numbers to “initialize the randomness”
function initializeRandom()
    randomNumber = getHour()/pow(10,6) -- change the 6 to a 10 when using second instead of hour in “getHour”
    
    local randomCounter = 100000
    while randomCounter > 0
    do
        getRandomNumber(1)
        randomCounter = randomCounter - 1
    end
end
```
