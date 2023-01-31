```js

// Die Methode forEach() ähnelt der Syntax "for(let i = 0; i < array.length, i++){} oder for(const value of array) {}". Sie durchläuft das Array in einer Schleife und führt den angegebenen Rückruf für jedes der Elemente des Arrays aus.

// Die an die "forEach"-Funktion übergebene Callback-Funktion kann die Werte "currentItem", "index", "array" annehmen.

const arr = [1, 2, 3, 4, 5, 6, 7, 8];
arr.forEach(val => console.log(val)); // val => console.log(val) <- callback function
// for(const val of arr) {
//	 console.log(val)
// }

// for(let i = 0;i < arr.length; i++) {
//	 console.log(arr[i])
// }


// ------------------------------------------- //
// Die Methode map() erstellt ein neues Array mit den Ergebnissen des Aufrufs einer bereitgestellten Funktion für jedes Element im aufrufenden Array.

// Die Methode arr.map ist eine der nützlichsten und am häufigsten verwendeten Methoden.
// Sie ruft die Funktion für jedes Element des Arrays auf und gibt das Array der Ergebnisse zurück.

// The syntax is:

// const result = arr.map(function(item, index, array) {
//   // returns the new value instead of item
// })

// Wenn wir über ein Array iterieren müssen - wir können forEach, for oder for..of verwenden.
// Wenn wir iterieren und die Daten für jedes Element zurückgeben müssen, können wir map verwenden.

const aRr = [1, 2, 3, 4, 5];
const squareArr = aRr.map(num => num ** 2);

console.log(squareArr);          // [ 1, 4, 9, 16, 25 ]

// Wir haben eine Funktion geschrieben, die das Quadrat einer Zahl zurückgibt, und diese Funktion als Argument an unsere map() übergeben

// ------------------------------ //

const numbers = [4, 9, 16, 25];

function mapMethod() {
    return numbers.map(Math.sqrt);
}

console.log(mapMethod());  // [ 2, 3, 4, 5 ]
console.log(numbers); // [ 4, 9, 16, 25 ]

// ------------------------------ //

const numArr2 = [1, 4, 9];

// 1.
const doubles = numArr2.map(function (num) {
    return num * 2;
})
console.log(doubles);   // [ 2, 8, 18 ]

// 2.
const doubles2 = numArr2.map(num => num * 2)

console.log(doubles2);       // [ 2, 8, 18 ]
console.log(numArr2);        // [ 1, 4, 9 ]


// ------------------------------ //

const lengths = ["Bilbo", "Gandalf", "Nazgul"].map(item => item.length);
console.log(lengths); // [ 5, 7, 6 ]

// ------------------------------ //

// Die Methode map() erstellt ein neues Array mit den Ergebnissen des Aufrufs einer Funktion für jedes Arrayelement.

// Die Methode map() ruft die angegebene Funktion einmal für jedes Element in einem Array auf, und zwar der Reihe nach.

// !!!map() führt die Funktion nicht für Array-Elemente ohne Werte aus.

// !!!map() verändert das ursprüngliche Array nicht.

// ------------------------------ //

//  Umformatierung von objectParamects in einem Array mit map

const newArray = [
    { key: 1, value: 10 },
    { key: 2, value: 20 },
    { key: 3, value: 30 }
];

const reformattedArray = newArray.map(objectParam => {
    const newObject = {};
    newObject[objectParam.key] = objectParam.value;
    return newObject;
});

console.log(reformattedArray);  // [ { '1': 10 }, { '2': 20 }, { '3': 30 } ]
console.log(newArray);          // [ { key: 1, value: 10 },
                                // { key: 2, value: 20 },
                                // { key: 3, value: 30 } ]


// ------------------------------ //

const anArr = "L 2 S 6 L 3 S 4".split(" ");

console.log(anArr); // [ 'L', '2', 'S', '6', 'L', '3', 'S', '4' ]

const newArr2 = anArr.map(item => {
    if (item === "L" || item === "S") {
        return item;
    } else {
        return item * 2;
    }
}).join(" ")

console.log(newArr2);   // L 4 S 12 L 6 S 8
```