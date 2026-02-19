# Moderner Lua Compiler

Da es für diese [alte S4 Lua Version](https://www.lua.org/manual/3.2/manual.html) keine Binärdateien gibt, hat sich MuffinMario die Mühe gemacht dies in einen modernen Compiler zu packen. Dies ist ein x86/x64 Standalone Lua 3.2.1 (Version in Siedler IV) Interpreter. \
Über die CMD könnt ihr so eure geschriebenen Scripte überprüfen und findet ggf. entsprechende Fehler die das Script brechen würden. Sobald es im Script einen Syntaxfehler gibt, läd Siedler4 das komplette Script nicht - jedoch bekommt ihr keine entsprechende Fehlermeldung. \
Um also euer Script auf Syntaxfehler zu überprüfen, geht am besten wie folgt vor:

* Legt den Compiler im selben Ordner wie euer Script ab. (Ihr müsst also das Script in einer externen Datei haben!)
* Öffnet die Kommandozeile ( **\[Win] + \[R]** und gebt dort "cmd" ein) und geht in das Verzeichnis eures Scripts und des Compilers. (Ordner wechseln macht ihr mit dem Befehle "cd")
* Führt nun mithilfe der Exe euer Script aus:\
  `luai.exe dateiname.lua`<br>

**Weitere Beispiele zur Ausführung in der Kommandozeile**

Zum schreiben in die Konsole:\
`luai`\
\
Ausführen einer Datei:\
`luai dateiname.lua`\
\
Interaktiver Modus in der Kommandozeile (Zum Beenden Strg+C):\
`luai -q (ohne dem > vor jeder eingegebenen Zeile)`\
`luai -i`\
\
Konsoleneingaben bis zum Beenden mit Strg+C als ein Skript gelesen bekommen:\
`luai -`



{% file src="../../.gitbook/assets/luai.zip" %}
