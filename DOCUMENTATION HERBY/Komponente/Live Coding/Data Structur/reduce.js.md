```js
// https://javascript.info/array-methods

// Die Methode reduce() führt eine (von Ihnen bereitgestellte) Reduzierfunktion auf jedem Element des Arrays aus, was zu einem einzigen Ausgabewert führt.

// Wenn wir über ein Array iterieren müssen, können wir forEach, for oder for..of verwenden.

// Wenn wir iterieren und die Daten für jedes Element zurückgeben müssen, können wir map verwenden.

// Die Methoden 'arr.reduce' und 'arr.reduceRight' werden verwendet, um einen einzelnen Wert auf der Grundlage des Arrays zu berechnen.

// Die Syntax lautet:

// const value = arr.reduce(function(previousValue, item, index, array) {
// // ...
// }, initial);

// Der von der Reduzierfunktion zurückgegebene Wert wird dem Akkumulator zugewiesen, 
// dessen Wert bei jeder Iteration im gesamten Array gespeichert wird und schließlich den endgültigen, einzigen Ergebniswert darstellt.

const numbers = [1, 2, 3, 4];

const sumReducer = (accumulator, currentValue) => accumulator + currentValue;
const sum = numbers.reduce(sumReducer);
console.log(sum); // 10

const sum2 = numbers.reduce(sumReducer, 5);

console.log(sum2); // 15

// ------------------------------ //

const arr = [1, 2, 3, 4, 5];
const result = arr.reduce((sum, current) => sum + current, 10); // 10 ist der aktuelle Wert, der an den ersten Callback übergeben wird
console.log(result); // 25

// ------------------------------ //

const reducer = function (akkumulator, currentValue, currentIndex, array) {
  console.log("acc ", akkumulator, "cv", currentValue, "ci", currentIndex, "arr ", array)
  return accumulator + currentValue;
}

arr.reduce(reducer);

// ------------------------------ //


let admins = [
    { id: "1", name: "Peter Fox", isAdmin: true },
    { id: "2", name: "Philipp Mattern", isAdmin: true },
    { id: "3", name: "Michael Hammer", isAdmin: true },
];

function groupById(array) {
	const reducerObj = (obj, value) => {
		obj[value.id] = value;
		return obj;
    }
    return array.reduce(reducerObj, {});

}

console.log(groupById(admins));

```