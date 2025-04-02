# SU.VersionOK

## SU.VersionOK(version)

Prüft, ob die lokal vorhandene Version der SU Library mindestens so hoch ist wie die angegebene Version.

⇒ Siehe [su-library.md](../tutorials/su-library.md "mention").

#### Parameter

* `version [String]`: Version der SU Library, die mindestens lokal vorhanden sein muss

#### Rückgabewert

* 1: die lokale Version ist ausreichend
* 0: sonst / Fehler

#### Beispiel

```lua
local versionOK = SU.VersionOK("0.4.2")
```
