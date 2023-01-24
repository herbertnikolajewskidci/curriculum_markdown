[[PB - Curriculum ENG]]

## Language

### Einführung ✔️

-   Was ist eine Programmiersprache?
-   Javascript oder ECMAscript? (kurze Geschichte von JS)
-   Interpretierte Sprachen vs. kompilierte Sprachen (kurzer Überblick)

### Variablen: Js-Dateien mit Node ausführen ✔️

-   Variablen: Einführung von `var`, `let`
-   Konstanten: Einführung in `const`
-   Deklaration und Zuweisung: `undefined` und `var` hissen
-   Ein Wort zu Namenskonventionen: camelCase vs. snake_case
-   Syntax-Debugging II: Nicht deklarierte Variablen

### Datentypen: Eine Einführung ✔️

-   Primitive Datentypen: Zahlen, Zeichenketten, Boolesche, Null und Undefiniert
-   Leere Variablen: `null` vs. `undefined`.
-   Objekte: Arrays und Objekte
-   Datentyp: der unäre Operator `typeof`

### Anweisungen ✔️

-   Definition einer Anweisung: Das Semikolon `;`
-   Hallo Welt: `Konsole.log(<Ausdruck>)`
-   Kommentare: `//`, `/* */`
-   Syntax Debugging I: Ungeschlossene Klammern

### Ausdrücke ✔️

-   String-Ausdrücke: einfache Anführungszeichen, doppelte Anführungszeichen, Verkettung
-   Mathematische Ausdrücke: +, -, \*, /, %
-   Boolesche Ausdrücke: Vergleichsoperatoren (`===, !==, >=, <=, >, <`)
-   Bedingte Ausdrücke: der ternäre Operator (Kombination der obigen Beispiele)

### Ändern von Variablen ✔️

-   Neuzuweisung von Variablen: `=`, `+=`, `-=`, Stringakkumulation
-   Zählen von Iterationen: die Zählervariable, `++`, `--`
-   Lesen eines Programms I (erste Einführung in den Zustand: Die Werte aller Variablen an einem bestimmten Punkt)
-   Bedingte Zuweisung mit dem ternären Operator
-   Syntax-Debugging III: Neuzuweisung von Konstanten

### Zeichenkette ✔️

-   Umgehung von Sonderzeichen: `\'`, `\`, `\n`
-   Syntaxfehlersuche IV: Zeichenketten und Anführungszeichen
-   String-Interpolation: Schablonenliterale, Verwendung von Ausdrücken innerhalb von Strings
-   Syntaxfehlersuche V: Nicht geschlossene Anführungszeichen
-   Ermitteln der Länge einer Zeichenkette: String.prototype.length
-   Ermitteln eines Zeichens in einer Zeichenkette: Klammerschreibweise
-   Syntaxfehlersuche VI: Nicht geschlossene Klammern

### Grundlegende String-Methoden ✔️

-   Groß- und Kleinschreibung umwandeln mit:

`String.prototype.toUpperCase()`, `String.prototype.toLowerCase()`

-   Extrahieren von Teilen eines Strings: `String.prototype.substring()`
-   Prüfen, ob eine Zeichenkette innerhalb einer anderen Zeichenkette liegt: `String.prototype.includes()`
-   Entfernen von Leerzeichen: `String.prototype.trim()`

### Zahl ✔️

-   Kombinieren von Strings und Zahlen mit +
-   Ganzzahlen vs. Fließkommazahlen
-   Konvertieren von Strings in Zahlen: `parseInt()`, `parseFloat()`
-   Modulo verwenden

### Mathematik ✔️

-   Aufrunden mit `Math.ceil()`
-   Abrunden mit `Math.floor()`
-   Ermitteln von Zufallszahlen mit `Math.random()`
-   Maximum und Minimum mit `Math.max()`, `Math.min()`

### Fallstricke bei Zahlen ✔️

-   Umgang mit NaN: `istNaN(<Ausdruck>)`, `typeof NaN`
-   Sehr lange Zahlen: `e`, Rundungsfehler
-   Umgang mit Rundungsfehlern: `Number.prototype.toFixed()`
-   Fallstricke bei der Division: Umgang mit `Unendlichkeit`

### Logisches Denken I ✔️

-   Einfache Präpositionsanalyse
-   Logische Operatoren: `&&`, `||`
-   Logik zum Lösen von Problemen verwenden; Wie funktioniert ein Förderband? oder Wie funktioniert eine Ampel?

### Boolean ✔️

-   Wahrheitsgemäße und falsche Werte: falsch, undefiniert, null, 0, ''
-   Typumwandlung: `==` vs. `===`
-   Syntax-Debugging VII: Verwendung von Zuweisung (`=`) statt Gleichheit (`===`)
-   Boolesche Invertierung mit `!`
-   Kurzschluss-Zuweisung: Zuweisung von Variablenrückfall mit `||`

### Array: Mehrere Werte unter einem Namen speichern ✔️

-   Zuweisung von Array-Literalen:

`const <Arrayname> = [<Wert 1>, <Wert 2>, ...]`

-   Zugriff auf Array-Elemente mit eckigen Klammern
-   Neuzuweisung von Array-Elementen mit eckigen Klammern
-   `const`s und Array-Elemente

### Grundlegende Array-Methoden ✔️

-   Auffinden von Elementen: `Array.prototype.indexOf(<Element>)`
-   Hinzufügen von Elementen: `Array.prototype.push()`, `Array.prototype.unshift()`
-   Entfernen von Elementen: `Array.prototype.pop()`, `Array.prototype.shift()`
-   Manipulieren von Arrays: `Array.prototype.reverse()`

---

## Programm

### Einführung ✔️

-   Der Ablauf eines Programms (von links nach rechts, von oben nach unten)

### Logisches Denken II ✔️

-   Was ist ein Algorithmus?
-   Analysieren von Problemen: Eingabe und Ausgabe
-   Lösungen finden: Algorithmen schreiben

### Entscheidungen ✔️

-   Bedingte Algorithmen
-   Die bedingte Anweisung: `if(<boolesch>){ ... }`
-   Syntax-Debugging VIII: Nicht geschlossene geschweifte Klammern
-   Der Standardfall: `else { ... }`
-   Lesen eines Programms II (Überspringen unerfüllter Fälle)

### Block-Scope ✔️

-   Code-Block-Definition: `if` Beispiel
-   Ein Wort zur Einrückung und Lesbarkeit
-   Bereichsdefinition: Unterschied zwischen `var`, `let`, `const`
-   Wann zu verwenden: `if` vs. ternärer Operator

### Multiple Choice ✔️

-   Testen mehrerer Bedingungen: `else if (<boolesch>){ ... }`
-   Ausführen von Code basierend auf einem Wert: `switch(<Ausdruck>){ ... }`
-   Wann zu verwenden: `switch` vs. `else if`

### Numerische Wiederholung ✔️

-   Wiederholung von Codeblöcken eine bestimmte Anzahl von Malen:

`for(<Anfangszustand>, <Endbedingung>, <Schritt>){ ... }`

-   Ausbrechen aus einer Schleife: `break;`
-   Überspringen einer Iteration: `continue;`
-   Komplexe Iterationen: Verschachtelte "for"-Schleifen
-   Syntax-Debugging VIII: Ungeschlossene geschweifte Klammern (wieder)

---

## Funktionen-I

### Einführung ✔️

-   Routinen und Unterroutinen (Funktionen)

### Aufrufen ✔️

-   Rückblick auf die bisher aufgerufenen Funktionen: `console.log()`, `parseInt()`, etc.
-   Der call stack (kurze Einführung)
-   Funktionsargumente

### Deklarieren ✔️

-   Deklarieren einer Funktion: `function <Name>(<Parameter>){ ... }`
-   Funktionsparameter: Benennung und Reihenfolge
-   Funktionsdeklarationen als Werte:

`const <Funktionsname> = function(<Parameter>){ ... }`

-   Pfeilfunktionskürzel:

`const <Funktionsname> = (<Parameter>) => { ... }`

### Funktionsgeltungsbereich ✔️

-   Parameter Geltungsbereich
-   Deklaration von Variablen in Funktionen
-   Globaler vs. lokaler Geltungsbereich: Neuzuweisung von Variablen in Funktionen
-   Lesen eines Programms IV (Funktionen nur lesen, wenn sie aufgerufen werden)

### Rückgaben und Nebeneffekte ✔️

-   Funktionsaufrufe als Werte: die Anweisung `return <Wert>;`
-   Definition von Seiteneffekten: Änderung des globalen Geltungsbereichs, Rückgriff auf äußere Geltungsbereiche
-   Reine Funktionsdefinition
-   Lesen eines Programms V (Ersetzen von Funktionsaufrufen durch ihren Rückgabewert)
-   Kürzere Pfeilfunktionen:

`const <Funktionsname> = (<Parameter>) => <Rückgabewert>`

### Fortgeschrittene Parameter ✔️

-   Standard-Parameterwerte:

`function(<parameter> = <Standardwert>) { ... }`

-   Variable Anzahl von Argumenten: Rest params - `...args`
-   Zugriff auf `args` mit Klammerschreibweise

---

## Data Structur

### Einleitung ✔️

-   Variablen und Beziehung zum Speicher

### Objekte: Speichern von mehreren Variablen in einem "namspace" ✔️

-   Der Typ eines Arrays: Arrays sind spezifische Objekte, `Array.isArray()`
-   Object literals: Definition von Eigenschaften

`const <Namensraum> = { <Schlüssel 1>: <Wert 1>, <Schlüssel 2>: <Wert 2>, ... }`

-   Zugriff auf Eigenschaften mit Klammerschreibweise (keine Variablen)
-   Zugriff auf Eigenschaften mit Punktschreibweise

### Objekt Scope ⬅️👀

-   Definition von Methoden: Methoden sind Eigenschaften mit Funktionswerten
-   Anwendung von Methoden: Überblick über die bisher verwendeten Methoden
-   Erstellen von Methoden
-   Objektliteraler Kontext: Methoden, `this` und `Function.prototype.bind()`

### Conversion and iterations

-   Iteration über Objekte: `for(let <property name> in <object name>){ ... }`
-   Eigenschaftsnamen in Array: `Object.keys(<object>)`
-   Iteration über Arrays: `for(let <value name> of <array name>){ ... }`
-   Zugriff auf Eigenschaften mit Klammerschreibweise (w. vars)
-   Eigenschaftswerte in Array: `Object.values(<object>)`

### Clones vs. References

-   Einfache Werte sind immer Klone: String, Zahl, Boolescher Wert
-   Objekte sind standardmäßig Referenzen: Array und Objektliterale
-   Shallow Cloning von Objekten und Arrays: der Spread-Operator `...`
-   Deep Cloning von Objekten und Arrays: rekursive Funktion

### Destructuring

-   Extrahieren von Werten aus Arrays: Array-Destrukturierungszuweisung
-   Extraktion von Werten aus Objekten: Objekt-Destrukturierungszuweisung
-   Benannte Funktionsparameter mit Objektdestrukturierung

### Nesting arrays and objects

-   Verschachtelung und Zugriff auf Arrays ineinander
-   Verschachtelung und Zugriff auf Objekte in Objekten
-   Lesen eines Programms VIII (die Eigenschaftskette)
-   Verschachtelung von und Zugriff auf Arrays in Objekten
-   Verschachtelung und Iteration über Objekte in Arrays

### Advanced Array methods

-   Iteration über Arrays: `Array.prototype.forEach(<function>)`
-   Konvertieren eines Arrays in ein anderes Array: `Array.prototype.map(<Funktion>)`
-   Konvertieren eines Arrays in einen einzelnen Wert: `Array.prototype.reduce(<Funktion>)`
-   Abrufen einer Teilmenge eines Arrays: `Array.prototype.filter(<Funktion>)`

### Logisches Denken III

-   Über die Komplexität von Algorithmen nachdenken: Big O Notation (sehr einfache Einführung)
-   Lesen komplexer Algorithmusbeispiele: Sortieren, kürzester Weg
-   Sortieren von Arrays mit `Array.prototype.sort(<Funktion>)`

---

## Funktionen-II

### Closure

-   Deklaration von Funktionen innerhalb von Funktionen
-   Verschachtelte Geltungsbereiche: Zugriff auf äußere Variablen
-   Erste Definition von Closure: Eine Funktion, die mindestens eine Variable und einen verschachtelten Bereich enthält
-   Funktionen höherer Ordnung I: Funktionen, die andere Funktionen zurückgeben
-   Lesen eines Programms VI (die Funktionsaufrufzwiebel)

### Rekursive Funktionen

-   Rekursive Algorithmen
-   Aufrufen einer Funktion aus sich selbst heraus
-   Stack overflow: Die Bedeutung der Exit-Bedingung
-   Lesen eines Programms VII (rekursiver Aufrufbaum)

### Callbacks

-   Funktionen höherer Ordnung II: Funktionen, die Funktionswerte annehmen (Callbacks)

---

## Klassen

### Klassen: Herstellung von Objekten mit der gleichen Struktur

-   Erstellen von Instanzen mit dem Schlüsselwort `new`, Die Klasse `Date`
-   Konstruieren eines Objekts: Die Methode `constructor()`, Instanz und `this`
-   Prototyp-Methoden: Hinzufügen eigener Methoden zu unserer Klasse
-   Erstellen von Unterklassen mit `extends` und `super()`
