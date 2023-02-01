[aus freeCodeCamp.org](https://www.freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/)

![Big O Cheat Sheet Bild](https://www.freecodecamp.org/news/content/images/size/w2000/2022/10/cover-template--12-.png)

#### **Ein Algorithmus ist eine Menge gut definierter Anweisungen zur Lösung eines bestimmten Problems. Diese Probleme können auf verschiedene Arten gelöst werden.**

Dies bedeutet, dass die Methode, die Sie verwenden, um zur gleichen Lösung zu gelangen, von meiner abweichen kann, aber wir sollten beide das gleiche Ergebnis erzielen.

Da es verschiedene Möglichkeiten gibt, ein Problem zu lösen, muss es eine Möglichkeit geben, diese Lösungen oder Algorithmen hinsichtlich ihrer Leistung und Effizienz (der Zeit, die Ihr Algorithmus zum Ausführen benötigt, und dem Gesamtspeicherbedarf) zu bewerten.

Dies ist für Programmierer entscheidend, um sicherzustellen, dass ihre Anwendungen ordnungsgemäß ausgeführt werden und ihnen dabei zu helfen, sauberen Code zu schreiben.

Hier kommt die Big O-Notation ins Spiel. Die Big O-Notation ist eine Metrik zur Bestimmung der Effizienz eines Algorithmus. Sie ermöglicht es Ihnen, zu schätzen, wie lange Ihr Code bei verschiedenen Eingabemengen läuft, und misst, wie effektiv Ihr Code skaliert, wenn die Größe Ihrer Eingabe zunimmt.

## Was ist Big O?

Big O, auch bekannt als Big O-Notation, repräsentiert die schlechtestmögliche Komplexität eines Algorithmus. Es verwendet algebraische Ausdrücke, um die Komplexität eines Algorithmus zu beschreiben.

Big O definiert die zum Ausführen eines Algorithmus erforderliche Laufzeit, indem es identifiziert, wie sich die Leistung Ihres Algorithmus ändert, wenn die Eingabegröße wächst. Es sagt jedoch nicht, wie schnell die Laufzeit Ihres Algorithmus ist.

Die Big O-Notation misst die Effizienz und Leistung Ihres Algorithmus mithilfe der Zeit- und Speicherkomplexität.

### Was ist Zeit- und Speicherkomplexität?

Ein wichtiger Faktor, der die Leistung und Effizienz Ihres Programms beeinflusst, ist die Hardware, das Betriebssystem und der CPU, die Sie verwenden.

Bei der Analyse der Leistung eines Algorithmus wird dies jedoch nicht berücksichtigt. Stattdessen zählt die Zeit- und Speicherkomplexität als Funktion der Größe der Eingabe.

Die Zeitkomplexität eines Algorithmus beschreibt, wie lange es dauern wird, den Algorithmus auszuführen, **als Funktion seiner Eingabegröße**. Ähnlich beschreibt die Speicherkomplexität eines Algorithmus die Gesamtmenge an Speicher oder Arbeitsspeicher, die erforderlich ist, um den Algorithmus auszuführen, **als Funktion der Größe der Eingabe**.

In dieser Anleitung werden wir uns auf die Zeitkomplexität konzentrieren. Dies ist ein ausführlicher Kurzreferenzleitfaden, der Ihnen hilft, zu verstehen, wie Sie die Zeitkomplexität für jeden Algorithmus berechnen können.

### Warum ist die Zeitkomplexität eine Funktion ihrer Eingabegröße?

Um das Konzept von "als Funktion der Eingabegröße" perfekt zu verstehen, stellen Sie sich vor, Sie haben einen Algorithmus, der die Summe von Zahlen auf Basis Ihrer Eingabe berechnet. Wenn Ihre Eingabe 4 ist, wird er 1+2+3+4 ausgeben und 10 ergeben; Wenn Ihre Eingabe 5 ist, wird es 15 ergeben (das bedeutet 1+2+3+4+5).

```js
const calculateSum = (input) => {
  let sum = 0;
  for (let i = 0; i <= input; i++) {
    sum += i;
  }
  return sum;
};
```


Im obigen Code haben wir drei Anweisungen:


![Schaubild Statements of code](https://paper-attachments.dropbox.com/s_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664881245657_Untitled.drawio+16.png)

Indem wir das obige Bild betrachten, haben wir nur drei Anweisungen. Trotzdem, da es eine Schleife gibt, wird die zweite Anweisung aufgrund der Eingabegröße ausgeführt, so dass, wenn die Eingabe vier ist, die zweite Anweisung (Anweisung 2) viermal ausgeführt wird, was bedeutet, dass der gesamte Algorithmus sechs (4 + 2) Mal ausgeführt wird.

In einfachen Worten, wird der Algorithmus **Eingabe + 2** Mal laufen, wobei Eingabe jede beliebige Zahl sein kann. Dies zeigt, dass es **in Bezug auf die Eingabe ausgedrückt wird. Mit anderen Worten, es ist eine Funktion der Eingabegröße.**

In Big O gibt es sechs Haupttypen von Komplexitäten (Zeit- und Speicherplatz):

-   Konstant: O(1)
-   Lineare Zeit: O(n)
-   Logarithmische Zeit: O(n log n)
-   Quadratische Zeit: O(n^2)
-   Exponentielle Zeit: O(2^n)
-   Faktorielle Zeit: O(n!)

Bevor wir Beispiele für jede Zeitkomplexität betrachten, sollten wir uns das Big O Zeitkomplexitätsdiagramm verstehen.

## Big O Komplexitätsdiagramm (Complexity Chart)

Das Big O-Diagramm, auch bekannt als Big O-Grafik, ist eine asymptotische Notation, die verwendet wird, um die Komplexität eines Algorithmus oder seine Leistung als Funktion der Eingabegröße auszudrücken.

Dies hilft Programmieren, den schlechtesten Fall zu identifizieren und das Ausführungszeit- oder Speicherbedarf eines Algorithmus vollständig zu verstehen.

Das folgende Diagramm illustriert die Big O-Komplexität:

![Big O Complexity Chart](https://paper-attachments.dropbox.com/s_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664885448372_Untitled.drawio+17.png)

Der Big O-Chart oben zeigt, dass O(1), was für eine konstante Zeitkomplexität steht, das Beste ist. Dies bedeutet, dass Ihr Algorithmus nur eine Anweisung ohne jegliche Iteration verarbeitet. Dann gibt es O(log n), das gut ist, und andere wie in der folgenden Liste gezeigt:

-   O(1) - Ausgezeichnet/Beste (Excellent/Best)
-   O(log n) - Gut (Good)
-   O(n) - Fair
-   O(n log n) - Schlecht (Bad)
-   O(n^2), O(2^n) und O(n!) - Furchtbar/Schlimmste (Horrible/Worst)

Sie verstehen nun die verschiedenen Zeitkomplexitäten und können die besten, guten und fairen erkennen sowie die schlechten und schlimmsten (vermeiden Sie immer die schlechte und schlimmste Zeitkomplexität).

Die nächste Frage, die in den Sinn kommt, ist, wie man weiß, welcher Algorithmus welche Zeitkomplexität hat, da dies eine Übersicht ("cheatsheet") sein soll 😂.

-   Wenn deine Berechnung nicht von der Größe der Eingabe abhängt, ist es eine konstante Zeitkomplexität (O(1)).
-   Wenn die Größe der Eingabe bei jedem Durchlauf halbiert wird, zum Beispiel bei der Iteration, Bearbeitung von Rekursion usw., ist es eine logarithmische Zeitkomplexität (O(log n)).
-   Wenn du nur eine Schleife in deinem Algorithmus hast, ist es eine lineare Zeitkomplexität (O(n)).
-   Wenn du verschachtelte Schleifen in deinem Algorithmus hast, also eine Schleife in einer Schleife, ist es eine quadratische Zeitkomplexität (O(n^2)).
-   Wenn der Wachstumsrate bei jeder Erhöhung der Eingabe verdoppelt wird, ist es eine exponentielle Zeitkomplexität (O2^n).

Lass uns mit der Beschreibung jeder Komplexität mit Beispielen beginnen. (Es ist wichtig zu beachten, dass ich in den Beispielen in diesem Leitfaden JavaScript verwenden werde, aber die Programmiersprache ist nicht wichtig, solange Sie das Konzept und jede Komplexität verstehen.)

## Big O Zeitkomplexitäts-Beispiele
### Konstante Zeitkomplexität: O(1)

Wenn Ihr Algorithmus nicht von der Einganggröße n abhängt, wird er als konstante Zeitkomplexität mit der Reihenfolge O(1) bezeichnet. Das bedeutet, dass die Laufzeit immer gleich bleibt, unabhängig von der Einganggröße.

Zum Beispiel, wenn ein Algorithmus das erste Element eines Arrays zurückgeben soll. Selbst wenn das Array 1 Million Elemente hat, wird die Zeitkomplexität konstant sein, wenn Sie diesen Ansatz verwenden:

```js
const firstElement = (array) => {
  return array[0];
};

let score = [12, 55, 67, 94, 22];
console.log(firstElement(score)); // 12
```

Die obige Funktion erfordert nur einen Ausführungsschritt, d. h. die Funktion läuft in konstanter Zeit mit der Zeitkomplexität O(1).

Aber wie ich bereits sagte, gibt es verschiedene Möglichkeiten, eine Lösung in der Programmierung zu erreichen. Ein anderer Programmierer könnte sich dafür entscheiden, zunächst eine Schleife durch das Array zu ziehen, bevor er das erste Element zurückgibt:

```js
const firstElement = (array) => {
  for (let i = 0; i < array.length; i++) {
    return array[0];
  }
};

let score = [12, 55, 67, 94, 22];
console.log(firstElement(score)); // 12
```

Dies ist nur ein Beispiel - wahrscheinlich würde das niemand tun. Aber wenn es eine Schleife gibt, ist dies nicht mehr konstante Zeit, sondern jetzt lineare Zeit mit der Zeitkomplexität O(n).

### Lineare Zeitkomplexität: O(n)

Von linearer Zeitkomplexität spricht man, wenn die Laufzeit eines Algorithmus linear mit der Größe der Eingabe zunimmt. Das bedeutet, dass eine Funktion mit einer Iteration, die über eine Eingabe der Größe n iteriert, eine Zeitkomplexität der Ordnung O(n) hat.

Ein Beispiel: Ein Algorithmus soll die Fakultät einer beliebigen eingegebenen Zahl zurückgeben. Das heißt, wenn Sie 5 eingeben, müssen Sie eine Schleife durchlaufen und 1 mal 2 mal 3 mal 4 und mal 5 multiplizieren und dann 120 ausgeben:

```js
const calcFactorial = (n) => {
  let factorial = 1;
  for (let i = 2; i <= n; i++) {
    factorial = factorial * i;
  }
  return factorial;
};

console.log(calcFactorial(5)); // 120
```

Die Tatsache, dass die Laufzeit von der Eingabegröße abhängt, bedeutet, dass die Zeitkomplexität linear mit der Ordnung O(n) ist.

### Logarithmische Zeitkomplexität: O(log n)

Dies ähnelt der linearen Zeitkomplexität, mit dem Unterschied, dass die Laufzeit nicht von der Eingabegröße abhängt, sondern von der Hälfte der Eingabegröße. Wenn die Eingabegröße bei jeder Iteration oder jedem Schritt abnimmt, spricht man von einem Algorithmus mit logarithmischer Zeitkomplexität.

Diese Methode ist die zweitbeste, da Ihr Programm für die Hälfte der Eingabegröße und nicht für die gesamte Größe läuft. Schließlich nimmt die Eingabegröße mit jeder Iteration ab.

Ein gutes Beispiel sind binäre Suchfunktionen, die Ihr sortiertes Array auf der Grundlage des Zielwerts teilen.

Nehmen wir an, Sie verwenden einen binären Suchalgorithmus, um den Index eines bestimmten Elements in einem Array zu finden:

```js
const binarySearch = (array, target) => {
  let firstIndex = 0;
  let lastIndex = array.length - 1;
  while (firstIndex <= lastIndex) {
    let middleIndex = Math.floor((firstIndex + lastIndex) / 2);

    if (array[middleIndex] === target) {
      return middleIndex;
    }

    if (array[middleIndex] > target) {
      lastIndex = middleIndex - 1;
    } else {
      firstIndex = middleIndex + 1;
    }
  }
  return -1;
};

let score = [12, 22, 45, 67, 96];
console.log(binarySearch(score, 96));
```

Da es sich im obigen Code um eine binäre Suche handelt, ermitteln Sie zunächst den mittleren Index Ihres Arrays, vergleichen ihn mit dem Zielwert und geben den mittleren Index zurück, wenn er gleich ist. Andernfalls müssen Sie prüfen, ob der Zielwert größer oder kleiner als der Mittelwert ist, um den ersten und letzten Index anzupassen und die Eingabegröße um die Hälfte zu reduzieren.

Da sich die Eingabegröße bei jeder Iteration um die Hälfte verringert, ist die Zeitkomplexität logarithmisch mit der Ordnung O(log n).

### Quadratische Zeitkomplexität: O(n^2)

Wenn man eine verschachtelte Iteration durchführt, d. h. eine Schleife in einer Schleife hat, ist die Zeitkomplexität quadratisch, was schrecklich ist.

Dies lässt sich am besten anhand eines Arrays mit n Elementen erklären. Die äußere Schleife wird n-mal ausgeführt, und die innere Schleife wird bei jeder Iteration der äußeren Schleife n-mal ausgeführt, was insgesamt n^2 Ausdrucke ergibt. Wenn das Array zehn Elemente hat, werden zehn 100 Mal gedruckt (10^2).

Hier ist ein Beispiel von [Jared Nielsen](https://jarednielsen.com/big-o-quadratic-time-complexity/), in dem Sie jedes Element in einem Array vergleichen, um den Index auszugeben, wenn zwei Elemente ähnlich sind:

```js
const matchElements = (array) => {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      if (i !== j && array[i] === array[j]) {
        return `Match found at ${i} and ${j}`;
      }
    }
  }
  return "No matches found 😞";
};

const fruit = ["🍓", "🍐", "🍊", "🍌", "🍍", "🍑", "🍎", "🍈", "🍊", "🍇"];
console.log(matchElements(fruit)); // "Match found at 2 and 8"
```

Im obigen Beispiel gibt es eine verschachtelte Schleife, was bedeutet, dass die Zeitkomplexität quadratisch mit der Ordnung O(n^2) ist.

### Exponentiale Zeitkomplexität: O(2^n)

Eine exponentielle Zeitkomplexität ergibt sich, wenn sich die Wachstumsrate mit jeder Addition zur Eingabe (n) verdoppelt, wobei häufig alle Teilmengen der Eingabeelemente durchlaufen werden. Jedes Mal, wenn sich eine Eingabeeinheit um 1 erhöht, verdoppelt sich die Anzahl der ausgeführten Operationen.

Die rekursive Fibonacci-Folge ist ein gutes Beispiel. Angenommen, Sie erhalten eine Zahl und möchten das n-te Element der Fibonacci-Folge finden.

Die Fibonacci-Folge ist eine mathematische Sequenz, in der jede Zahl die Summe der beiden vorangehenden Zahlen ist, wobei 0 und 1 die ersten beiden Zahlen sind. Die dritte Zahl in der Folge ist die 1, die vierte die 2, die fünfte die 3 und so weiter... (0, 1, 1, 2, 3, 5, 8, 13, ...).

Das bedeutet, dass das 6. Element der Fibonacci-Folge die 8 ist, wenn Sie die 6 eingeben:

```js
const recursiveFibonacci = (n) => {
  if (n < 2) {
    return n;
  }
  return recursiveFibonacci(n - 1) + recursiveFibonacci(n - 2);
};

console.log(recursiveFibonacci(6)); // 8
```

Im obigen Code legt der Algorithmus eine Wachstumsrate fest, die sich jedes Mal verdoppelt, wenn der Eingabedatensatz hinzugefügt wird. Dies bedeutet, dass die Zeitkomplexität exponentiell mit einer Ordnung O(2^n) ist.

## Zusammenfassung

In diesem Leitfaden haben Sie gelernt, was es mit der Zeitkomplexität auf sich hat, wie die Leistung mit Hilfe der Big-O-Notation bestimmt wird und welche verschiedenen Zeitkomplexitäten es gibt, mit Beispielen.

Sie können mehr über den Lehrplan [JavaScript Algorithms and Data Structures](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) von freeCodeCamp lernen.

Viel Spaß beim Lernen!

---
Übersetzt von: Herby (mit Hilfe von ChatGPT & DeepL)

Link zum Ursprünglichen Artikel: https://freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/

Ursprünglichen Autor:
![Pic von Joel Olawanle](https://www.freecodecamp.org/news/content/images/size/w60/2022/06/1654890413623.jpg) **Joel Olawanle**
Frontend Developer & Technical Writer

---