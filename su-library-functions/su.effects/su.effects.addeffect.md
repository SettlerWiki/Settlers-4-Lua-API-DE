---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Effects.AddEffect

## SU.Effects.AddEffect(effectID, x, y, delayTicks, durationTicks=SU.Time.TICKS\_PER\_SECOND, soundID=Sounds.NO\_SOUND, playSoundEverywhere=0)

Fügt den angegebenen Effekt hinzu. Anders als bei [effects.addeffect.md](../../library-functions/effects/effects.addeffect.md "mention") kann hier die genaue Dauer eingestellt werden.

**Achtung**: entspricht die angegebene Dauer nicht einem Vielfachen der wirklichen Dauer des Effekts, wird der Effekt einfach abgebrochen!

⇒ Im **Normalfall** ist es **besser** [effects.addeffect.md](../../library-functions/effects/effects.addeffect.md "mention") zu **verwenden**!

#### Parameter

* `effectID`: [effects.md](../../api-enums/effects.md "mention")
* `x, y`: Koordinaten
* `delayTicks`: Verzögerung in Ticks (siehe [su.time.md](../../su-api-enums/su.time.md "mention"))
* `durationTicks` (optional): Dauer in Ticks (siehe [su.time.md](../../su-api-enums/su.time.md "mention"))
* `soundID` (optional): [sounds.md](../../api-enums/sounds.md "mention")
* `playSoundEverywhere` (optional): bei 1 wird der Sound abgespielt, egal wo der Bildschirm gerade ist - mit Vorsicht zu genießen!

#### Beispiel

<pre class="language-lua"><code class="lang-lua"><strong>-- spielt den Effekt Effects.MAGIC_PILE01 nach 40 Ticks 100 Ticks lange ab
</strong><strong>SU.Effects.AddEffect(Effects.MAGIC_PILE01, 300, 130, 40, 100)
</strong></code></pre>
