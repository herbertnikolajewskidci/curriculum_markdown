```js
console.log(Math.max(3, 5, 1)); // 5

// Nehmen wir nun an, wir haben ein Array [3, 5, 1]. Wie können wir Math.max damit aufrufen?

// Die Übergabe "so wie sie ist" wird nicht funktionieren, da Math.max eine Liste numerischer Argumente erwartet, nicht ein einzelnes Array:

const arr = [3, 5, 1];

console.log(Math.max(arr)); // NaN

// Und sicherlich können wir die Elemente im Code nicht manuell auflisten Math.max(arr[0], arr[1], arr[2]), da wir nicht wissen, wie viele es sind. 
// Während unser Skript ausgeführt wird, könnten es viele sein, oder auch keine. Und das würde hässlich werden.

// Die Spread-Syntax ist die Rettung!

// ---------------------------------------------- //

// Die Spread-Syntax sieht ähnlich aus wie Rest-Parameter und verwendet ebenfalls ..., bewirkt aber genau das Gegenteil.
// Wenn ...arr im Funktionsaufruf verwendet wird, "expandiert" sie ein iterierbares Objekt arr in die Liste der Argumente.
// Die Spread-Syntax arbeitet nur mit Iterables.

const numbers = [3, 5, 1];

console.log(Math.max(...numbers)); // 5 (spread verwandelt ein array in eine Liste von Argumenten)

// ---------------------------------------------- //

// **HINWEIS*** Sehr, sehr häufig wird die Spread-Syntax einfach als 
// "Spreadoperator" bezeichnet, aber MDN bezeichnet die drei Punkte die "Spreadsyntax", und
// er ist in der Liste der Operatoren enthalten!
// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax

// ---------------------------------------------- //
// !!!Die Spread-Syntax operiert mit Iterables oder Objekten

// Iterables
// Zeichenketten, Array
// "abcd", [1, 2, 3, wahr, falsch]
//
// Objekt 
//{Vorname: "John", Nachname: "Doe"}

// noniterables:
// boolean number null undefined
// true 245 null undefined
// ---------------------------------------------- //

// Wir können auf diese Weise auch mehrere Iterables übergeben:
let arr1 = [1, -2, 3, 4];
let arr2 = [8, 3, -8, 1];

console.log(Math.max(...arr1, ...arr2)); // 8

// ---------------------------------------------- //

// Wir können die Spread-Syntax auch mit normalen Werten kombinieren:
arr1 = [1, -2, 3, 4];
arr2 = [8, 3, -8, 1];

console.log(Math.max(1, ...arr1, 2, ...arr2, 25)); // 25

// ---------------------------------------------- //

// Auch die Spread-Syntax kann verwendet werden, um Arrays zusammenzuführen:

const arr3 = [3, 5, 1];
const arr4 = [8, 9, 15];

const mergedArray = [...arr3, ...arr4];
const mergedArray2 = [0, ...arr3, 2, ...arr4];

console.log(mergedArray); // [ 3, 5, 1, 8, 9, 15 ]
console.log(mergedArray2); // [ 0, 3, 5, 1, 2, 8, 9, 15 ]

const clonedArr3 = arr3;
console.log(clonedArr3); // [ 3, 5, 1 ]

// ---------------------------------------------- //

// In den obigen Beispielen haben wir zur Veranschaulichung der Spreadsyntax ein Array verwendet, aber jede beliebige Iterationsform ist geeignet.

// Hier verwenden wir zum Beispiel die Spread-Syntax, um die Zeichenkette in ein Array von Zeichen zu verwandeln:

const str = "Hallo";

console.log([...str]); // H,e,l,l,o

// ODER

// let spreadStr = ...str; // Fehler!!
const spreadStr = [...str];
console.log(spreadStr); // [ 'H', 'e', 'l', 'l', 'o' ]

const spreadStr2 = { ...str };
console.log(spreadStr2); // { '0': 'H', '1': 'e', '2': 'l', '3': 'l', '4': 'o' }

// wird nicht funktionieren!
const spreadStr3 = "...str";
console.log(spreadStr3); // ...str

// ---------------------------------------------- //
function iAmAFunction(param1, param2, ...rest) {
  console.log(rest); // [ 'a', 'nice', 'day', '!' ]
}

iAmAFunction("Hallo", "haben", "a", "schön", "Tag", "!");

// ---------------------------------------------- //
// 1. Erstellen Sie eine Funktion, die die Summe aller Argumente zurückgibt (unabhängig davon, wie viele Argumente es gibt)


function sumAll(...num) { // Restparameter wird im Argument übergeben
  let sum = 0;
  console.log("num arr spreaded in the function call", num);
  // num arr verteilt im Funktionsaufruf [ 2, 4, 6, 8, 21, 456 ]

  for (let i = 0; i < num.length; i++) {
    sum += num[i];
  }
  // console.log(args);  
  return sum;
}

const myNumbers = [2, 4, 6, 8, 21, 456];
const myNumbers3 = [2, 4, 6, 8, 21, 456, 645];

// Die  Verwendung der Spread-Syntax in einem Funktionsaufruf zur Übergabe eines Arrays von Zahlen
console.log(sumAll(...myNumbers)); // 497
console.log(sumAll(...myNumbers, ...myNumbers3)) // 1639
```