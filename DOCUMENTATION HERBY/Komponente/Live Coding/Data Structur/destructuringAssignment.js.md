```js
// Destructuring Assignment (Destrukturierung Zuweisung)
// Die beiden am häufigsten verwendeten Datenstrukturen in JavaScript sind Object und Array.

// Mit Objekten können wir eine einzelne Einheit erstellen, die Datenelemente nach Schlüssel speichert, und mit Arrays können wir Datenelemente in einer geordneten Sammlung sammeln.

// Wenn wir diese jedoch an eine Funktion übergeben, benötigt diese möglicherweise nicht ein Objekt/Array als Ganzes, sondern eher einzelne Teile.

// Die Destrukturierungszuweisung (destructuring assignment) ist eine spezielle Syntax, die es uns ermöglicht, Arrays oder Objekte in eine Reihe von Variablen zu "entpacken", da dies manchmal bequemer ist. Die Destrukturierung eignet sich auch hervorragend für komplexe Funktionen mit vielen Parametern, Standardwerten usw.

// Array-Destrukturierung
// Wie das Array in Variablen destrukturiert wird:

// 1.
const arr = ["Ilja", "Kantor"];

// Zuweisung zur Destrukturierung
const [vorname, nachname] = arr;
// setzt vorname = arr[0]
// und nachname = arr[1]

// const vorname = arr[0];
// const nachname = arr[1];

console.log(vorname); // Ilja
console.log(nachname); // Kantor

// Man nennt es "destrukturierende Zuweisung", weil es durch das Kopieren von Elementen in Variablen "destrukturiert" wird. Das Array selbst wird jedoch nicht verändert.
console.log(arr);

// ---------##---------

// wenn das zweite und letzte Element nicht benötigt wird.
// das zweite Element des Arrays wird übersprungen, das dritte wird title zugewiesen, und der Rest der Arrayelemente wird ebenfalls übersprungen (da es keine Variable für sie gibt).

const [firstName2, , title] = [
    "Julius",
    "Caesar",
    "Konsul",
    "der römischen Republik",
];

console.log(title); // Konsul

// ---------##---------

const [c, , e, f] = [44, 66, 88, 99];

console.log(c);
console.log(e);
console.log(f);
// WIR KÖNNEN SOGAR ZAHLEN / TEILE ÜBERSPRINGEN; DIE UNS NICHT INTERESSIEREN

// ---------##---------

// Wir können es mit jeder iterable verwenden, nicht nur mit Arrays:

const [var1, var2, var3] = "abc";

console.log(var1);
console.log(var2);
console.log(var3);

// ---------##---------

const europeanCities = ["Paris", "london"];
const asianCities = ["Shanghai", "Tokio"];
const twoArrays = [...europeanCities, ...asianCities];

console.log(twoArrays); // [ 'Paris', 'london', 'Shanghai', 'Tokio' ]

// ---------##---------

// wenn wir ein sehr langes Array haben
const alphabet = ["a", "b", "c", "d", "e", "f", "g", "h"];
// const letterA = alphabet[0];
// const letterB = alphabet[1];
// const letterF = alphabet[5];

// mach es sinn, es so zu kürzen
const [letterA, letterB, , , , letterF] = alphabet; // empfohlen für Arrays

console.log(letterA);
console.log(letterB);
console.log(letterF);

// const [letterA, letterB, ...rest] = alphabet;
// console.log(rest); // [ 'c', 'd', 'e', 'f', 'g', 'h' ]

// ---------##---------
// Destrukturierung von Objekten

const user = {};
[user.name, user.lastName] = "Ilja Kantor".split(" ");
// const [userName2, userLastName2] = "Ilja Kantor".split(" ");
// user.name = userName2;
// user.lastName = userLastName2;

console.log(user.name); // Ilja
console.log(user.lastName); // Kantor
console.log(user); // { name: 'Ilja', lastName: 'Kantor' }

// ---------##---------
// Objektdestrukturierung muss gleichen Bezeichner haben

// let i;
// let j;
let i, j; // "Assignables"

({ i, j } = {
    i: 10,
    j: 20,
});

// wir erzeugen einzelne Variablen i, j
console.log(i); // 10
console.log(j); // 20

// ---------##---------

let k, l, m;
({ k, l, ...m } = {
    k: 10,
    l: 20,
    o: 40,
    p: 100,
});
console.log(m);

// const { r, t, ...z } = {
//     r: 10,
//     t: 20,
//     o: 40,
//     p: 100,
// };
// console.log(z);

// let arr2 = [];
// ({ k: arr2[0], l: arr2[1] } = {
//     k: 10,
//     l: 20,
//     o: 40,
//     p: 100,
// });

// console.log(arr2);

// ---------##---------
// Funktion ohne Destrukturierung

function easyFunction(array) {
    const num1 = array[0];
    const num2 = array[1];
    const num3 = array[2];
    const num4 = array[3];

    return num1 + num2 + num3 + num4;
}

console.log(easyFunction([1, 2, 3, 4])); // 10

// ---------##---------
// Destrukturierung in Funktionen

// Funktion mit Destrukturierung
function destructureFunction(arr) {
    const [num1, num2, num3, num4] = arr;
    return num1 + num2 + num3 + num4;
}

console.log(destructureFunction([1, 2, 3, 4])); // 10

// kürzere Funktion mit Destrukuturierung
function destructureFunction2([num1, num2, num3, num4]) {
    // Entpacken mit Destrukturierung
    return num1 + num2 + num3 + num4;
}

// ---------##---------
// REACT

const stateObject = {
    name: "Martina",
    age: 36,
};
// häufigerer Fall: vordefinierte Eigenschaftsnamen müssen wiederverwendet werden, damit das destructuring in einer Parameter übergabe funktionert.
function myReactFunction({ name, age }) {
    console.log(`Mein Namen ist ${name} und ich bin ${age} Jahre alt.`);
}

myReactFunction(stateObject);

```