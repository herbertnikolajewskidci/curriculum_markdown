## Einleitung
Recursion ist eine Technik in der Programmierung, bei der eine <u>Funktion sich selbst aufruft,</u> um ein bestimmtes Problem zu lösen. Die Funktion splittet das Problem in kleinere Teilprobleme, die <u>sie dann selbst löst, bis das ursprüngliche Problem vollständig gelöst ist.</u>

In JavaScript wird Recursion häufig bei der Lösung von Problemen verwendet, die sich rekursiv aufteilen lassen, wie z.B. das <u>Durchlaufen eines Baumes oder einer Liste.</u> Eine wichtige Regel bei der Verwendung von Rekursion ist es, eine <u>Abbruchbedingung</u> zu haben, um zu vermeiden, dass die<u> Funktion endlos aufruft und einen Fehler verursacht.</u>

Mit dem Verständnis von Recursion kann man effizientere und lesbarere Lösungen für bestimmte Probleme schreiben, allerdings sollte man immer über die Leistungsauswirkungen im Klaren sein, da Rekursion oft langsamer ist als Iterationen.

**Metapher:** Recursion ist eine Programmiertechnik, bei der eine Funktion sich selbst immer wieder aufruft, um eine bestimmte Aufgabe zu erfüllen. Es ist wie ein Spiel, bei dem du eine Aufgabe hast und jedes Mal, wenn du diese Aufgabe erfüllt hast, noch eine weitere, ähnliche Aufgabe bekommst. Dies geht so lange weiter, bis du endlich die letzte Aufgabe erfüllt hast.

Zum Beispiel kannst du dir vorstellen, dass du in einem Zimmer voller Bücher eine bestimmte Geschichte suchst. Du siehst dir das erste Buch an und findest die Geschichte nicht. Dann gehst du zum nächsten Buch und siehst es dir an. Wenn du die Geschichte nicht findest, gehst du zum nächsten Buch usw. Bis du endlich die Geschichte findest.

Das ist genau das, was eine rekursive Funktion macht. Es sieht sich eine Aufgabe an und wenn es sie nicht lösen kann, gibt es sich selbst eine ähnliche, kleinere Aufgabe. Bis es endlich die Lösung findet.

1.  Recursive Functions:
```js
function print(n) {

  if (n === 0) return; // Abbruchbedingung
  
  console.log(n); // Funktionslogik
  
  print(n-1); // Funktionsaufruf innerhalb der Funktion
  
}

print(5); // 5 4 3 2 1
```

Diese Funktion nimmt eine Zahl als Argument und gibt sie aus. Wenn die Zahl 0 erreicht ist, wird die Funktion beendet. Andernfalls ruft sich die Funktion selbst mit n-1 auf, bis die Abbruchbedingung erfüllt ist.

---

2.  Rekursive Algorithmen:
```js
function sum(n) {
  if (n === 1) return 1;
  return n + sum(n-1);
}
console.log(sum(5)); // 15
```
Diese Funktion berechnet die Summe aller Zahlen von 1 bis n. Wenn n gleich 1 ist, wird 1 zurückgegeben. Ansonsten wird n zur aktuellen Summe hinzugefügt und die Funktion ruft sich selbst mit n-1 auf, bis die Abbruchbedingung erfüllt ist.

Die Alternative als For-Loop:
```js
function sum(n) {
  let result = 0;
  for (let i = 1; i <= n; i++) {
    result += i;
  }
  return result;
}
console.log(sum(5)); // 15
```

---

3.  Funktionsaufruf innerhalb der Funktion:
```js
function countdown(n) {
  console.log(n);
  if (n <= 0) return;
  countdown(n-1);
}
countdown(5); // 5 4 3 2 1 0
```
Hier sehen wir eine rekursive Funktion zum Herunterzählen von Zahlen. Die Funktion gibt die aktuelle Zahl aus und ruft sich selbst dann mit n-1 auf, bis die Abbruchbedingung erfüllt ist (n <= 0).

For-Loop Alternative:
```js
function countdown(n) {
  for (let i = n; i >= 0; i--) {
    console.log(i);
  }
}
countdown(5); // 5 4 3 2 1 0

```


---

4.  Stack Overflow: Bedeutung der Abbruchbedingung:
```js
function infiniteLoop() {
  infiniteLoop();
}
infiniteLoop(); // Stack overflow error
```
Hier sehen wir eine rekursive Funktion, die sich unendlich selbst aufruft und so einen Stack Overflow auslöst. Da keine Abbruchbedingung vorhanden ist, wird die Funktion unendlich oft aufgerufen, bis der Speicher des Stacks voll ist.

---

5.  Lesen eines Programms VII (rekursive Aufrufbaum):
```js
function callTree(n) {
  console.log(n);
  if (n >= 3) return;
  callTree(n+1);
}
callTree(1);
// 1
// 2
// 3
```
Hier sehen wir einen rekursiven Aufrufbaum. Die Funktion ruft sich selbst mit n+1 auf, bis die Abbruchbedingung erfüllt ist (n >= 3). Wir können sehen, wie die Funktion jedes Mal aufgerufen wird, bis die Abbruchbedingung erfüllt ist.

---

Weitere Beispiel:


Reihenfolge in String umkehren:
```js
function reverseString(str) {
  if (str.length <= 1) return str;
  return reverseString(str.slice(1)) + str[0];
}
console.log(reverseString("hello")); // olleh
```
1.  Die Funktion `reverseString` nimmt einen String `str` als Argument.
2.  Die if-Bedingung prüft, ob die Länge des Strings `str` kleiner oder gleich 1 ist. Wenn dies der Fall ist, wird der String zurückgegeben.
3.  Wenn die Bedingung nicht erfüllt ist, ruft die Funktion sich selbst auf mit `str.slice(1)`, was den Teil des Strings ohne das erste Zeichen zurückgibt.
4.  Die Rückgabe des Funktionsaufrufs von `reverseString(str.slice(1))` wird mit dem ersten Zeichen des Strings `str[0]` verbunden.
5.  Das Ergebnis, also die Umkehrung des ursprünglichen Strings, wird zurückgegeben.


For-Loop Alternative
```js
function reverseStringForLoop(str) {
  const reversed = '';
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
  return reversed;
}
console.log(reverseStringForLoop("hello")); // olleh
```
Wir legen eine leere Zeichenfolge namens `reversed` an und fügen in jedem Schleifendurchlauf das letzte Zeichen des ursprünglichen Strings hinzu. Am Ende haben wir eine umgekehrte Zeichenfolge.

---

Reihenfolge in Array umkehren:
```js
function reverseArrayRecursion(arr) {
  if (arr.length <= 1) return [arr[0]];
  const result = reverseArrayRecursion(arr.slice(1));
  result.push(arr[0]);
  return result;
}
console.log(reverseArrayRecursion([1, 2, 3, 4, 5])); // [5, 4, 3, 2, 1]
```

1.  `reverseArrayRecursion` ist eine rekursive Funktion, die ein Array als Argument entgegennimmt.
2.  In der ersten Zeile wird eine Abbruchbedingung überprüft. Wenn die Länge des Arrays 1 oder weniger beträgt, wird das einzige Element des Arrays in einem neuen Array zurückgegeben.
3.  In der nächsten Zeile wird eine lokale Variable `result` definiert, die durch einen rekursiven Aufruf von `reverseArrayRecursion` erzeugt wird. Dabei wird das Array um ein Element gekürzt und erneut aufgerufen.
4.  Die letzte Zeile fügt das erste Element des ursprünglichen Arrays an das Ende von `result` an und gibt es zurück.
5.  Dieser Prozess wird rekursiv fortgesetzt, bis die Abbruchbedingung erreicht ist. Am Ende wird das resultierende Array mit den umgekehrten Elementen des ursprünglichen Arrays zurückgegeben.
6.  Die Ausgabe zeigt das resultierende Array mit den umgekehrten Elementen des ursprünglichen Arrays.

For-Loop Alternative:
```js
function reverseArrayForLoop(arr) {
  const reversed = [];
  for (let i = arr.length - 1; i >= 0; i--) {
    reversed.push(arr[i]);
  }
  return reversed;
}
console.log(reverseArrayForLoop([1, 2, 3, 4, 5])); // [5, 4, 3, 2, 1]
```

---

