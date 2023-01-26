```js
// Destructuring Assignment (Destrukturierung Zuweisung)
// Die beiden am häufigsten verwendeten Datenstrukturen in JavaScript sind Object und Array.

// Mit Objekten können wir eine einzelne Einheit erstellen, die Datenelemente nach Schlüssel speichert, und mit Arrays können wir Datenelemente in einer geordneten Sammlung sammeln.

// Wenn wir diese jedoch an eine Funktion übergeben, benötigt diese möglicherweise nicht ein Objekt/Array als Ganzes, sondern eher einzelne Teile.

// Die Destrukturierungszuweisung (destructuring assignment) ist eine spezielle Syntax, die es uns ermöglicht, Arrays oder Objekte in eine Reihe von Variablen zu "entpacken", da dies manchmal bequemer ist. Die Destrukturierung eignet sich auch hervorragend für komplexe Funktionen mit vielen Parametern, Standardwerten usw.


// Array-Destrukturierung
// Wie das Array in Variablen destrukturiert wird:

// 1.
const arr = ["Ilja", "Kantor"]

// Zuweisung zur Destrukturierung
// const [vorname, nachname] = arr;
// setzt vorname = arr[0]
// und nachname = arr[1] 

const vorname = arr[0];
const nachname = arr[1];

console.log(vorname); // Ilja
console.log(nachname); // Kantor

// Man nennt es "destrukturierende Zuweisung", weil es durch das Kopieren von Elementen in Variablen "destrukturiert". Das Array selbst wird jedoch nicht verändert.
console.log(arr); // [ 'Ilya', 'Kantor' ]

// ---------##---------

// 2.
// wenn das zweite Element nicht benötigt wird.
// das zweite Element des Arrays wird übersprungen, das dritte wird title zugewiesen, und der Rest der Arrayelemente wird ebenfalls übersprungen (da es keine Variablen für sie gibt).
const [firstName2, , title] = ["Julius", "Caesar", "Konsul", "der römischen Republik"];

console.log(title); // Konsul

// ---------##---------

// 3.
const [c, , e, f] = [44, 66, 88, 99]; // Sprung über 66 
console.log(c); // 44
console.log(e); // 88
console.log(f); // 99
// WIR KÖNNEN SOGAR ZAHLEN / TEILE ÜBERSPRINGEN, DIE UNS NICHT INTERESSIEREN

// ---------##---------
// 4. 
// Wir können es mit jeder iterable verwenden, nicht nur mit Arrays:

const [var1, var2, var3] = "abc"; // ["a", "b", "c"]
console.log(var1); // a
console.log(var2); // b
console.log(var3); // c
console.log(typeof var1) // string

// ---------##---------
// 5.

const europeanCitiy = ['Paris', 'london'];
const asiatischeStädte = ['Shanghai', 'Tokio'];
const twoArrays = [...europeanCitiy, ...asianCities]; // Destrukturierung
// Wir können auf mehr als eine rechts zugreifen

console.log(twoArrays); // [ 'Paris', 'London', 'Shanghai', 'Tokio' ]

// ---------##---------
// 6.

// wenn wir ein sehr langes Array haben 
const alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'];
// const letterA = alphabet[0];
// const letterB = alphabet[1];
// const letterF = alphabet[5];

// macht es Sinn, es so zu kürzen
const [letterA, letterB, , , , letterF] = alphabet; // empfohlen für Arrays 
console.log(buchstabeA);
console.log(BuchstabeB);
console.log(buchstabeF);

// ---------##---------
// Destrukturierung von Objekten
// 7.

const user = {};
[user.name, user.nachname] = "Ilja Kantor".split(' ');

console.log(benutzer.name); // Ilja
console.log(benutzer.nachname); // Kantor
console.log(user); // { name: 'Ilya', nachname: 'Kantor' }

// ---------##---------
// 8.
// Objektdestrukturierung muss gleichen Bezeichner haben

let i, j; // "Assignables"
({ i, j } = {
    i: 10,
    j: 20
});

// wir erzeugen einzelne Variablen i, j 

console.log(i); // 10
console.log(j); // 20

console.log(typeof i); // Zahl

// ---------##---------
// 9.

let k, l, m;
({ k, l, ...m } = {
    k: 10,
    l: 20,
    o: 40,
    p: 100
});
console.log(m); // { o: 40, p: 100 }

// ---------##---------
// 10.

// Funktion ohne Destrukturierung 
function easyFunction(array) {
    const num1 = array[0];
    const num2 = array[1];
    const num3 = array[2];
    const num4 = array[3];
    return (zaehl1 + zaehl2 + zaehl3 + zaehl4)
}
console.log(easyFunction([1, 2, 3, 4])); // 10

// ---------##---------
// Destrukturierung in Funktionen

function easyFunction(arr) { // Funktion ohne Destrukturierung
    const num1 = arr[0];
    const num2 = arr[1];
    const num3 = arr[2];
    const num4 = arr[3];

    return (num1 + num2 + num3 + num4);
}

console.log(easyFunction([1, 2, 3, 4])); // 10


function destructureFunction(arr) { // Funktion mit Destrukturierung
    const [num1, num2, num3, num4] = arr;

    return (num1 + num2 + num3 + num4);
}

console.log(destructureFunction([1, 2, 3, 4])); // 10


function destructureFunction2([num1, num2, num3, num4]) { // kürzere Funktion mit Destructuring
    // Entpacken mit Destrukturierung
    return (num1 + num2 + num3 + num4);
}

console.log(destructureFunction2([1, 2, 3, 4])); // 10

// ---------##---------
// 12.

// REACT
const stateObject = {
    name: 'Martina',
    age: 36
};
// häufigerer Fall: vordefinierte Eigenschaftsnamen müssen wiederverwendet werden
function myReactFunction({ name, age }) {
    console.log(`Mein Name ist ${name} und ich bin ${age} Jahre alt`);
}
myReactFunction(stateObject); // Mein Name ist Martina und ich bin 36 Jahre alt.
```