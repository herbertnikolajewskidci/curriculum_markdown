```js
// https://javascript.info/array-methods

// Die Methode filter() erzeugt ein neues Array mit allen Elementen, die den von der angegebenen Funktion implementierten Test bestehen.

// Die Methode filter() erzeugt ein Array, das mit allen Arrayelementen gefüllt wird, die einen (als Funktion bereitgestellten) Test bestehen.

// filter() führt die Funktion nicht für Array-Elemente ohne Werte aus.

// filter() verändert das ursprüngliche Array nicht.

const numbers = [1, 2, 3, 4, 5];

const oddNumbers = numbers.filter(num => num % 2 === 0);

console.log(oddNumbers); // [2, 4]

// Die Filterfunktion hat eine Funktion, die true zurückgibt, wenn eine Zahl gerade ist. 
// Die Funktion filter() "filtert" das Eingabe-Array basierend darauf, ob das Element wahr oder falsch ist. 

// ------------------------------ //

const ages = [32, 33, 16, 40];

function checkAdult(age) {
  return age >= 18;
}

const isAllowed = ages.filter(checkAdult);

console.log(isAllowed); // [ 32, 33, 40 ]

// ------------------------------ //

const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result); // ["exuberant", "destruction", "present"]
// ------------------------------ //

// 1.
function isBigEnough(wert) {
  return wert >= 10;
}

const filtered = [12, 5, 8, 130, 44].filter(isBigEnough);

console.log(gefiltert); // [ 12, 130, 44 ]

// 2.
const gefiltert2 = [12, 5, 8, 130, 44].filter(wert => wert >= 10);

console.log(gefiltert2); // [ 12, 130, 44 ]

// ------------------------------ //

const fruits = ['apple', 'banana', 'grapes', 'mango', 'orange'];

/**
 * Filtert Array-Elemente basierend auf Suchkriterien (Query)
 */
function filterItems(arr, abfrage) {
  return arr.filter(element => element.toLowerCase().indexOf(query.toLowerCase()) !== -1)
}

console.log(filterItems(fruits, 'ap')); // ['apple', 'grapes']
console.log(filterItems(fruits, 'an')); // ['banana', 'mango', 'orange']
console.log(filterItems(fruits, "z")); // []

// ------------------------------ //
```

