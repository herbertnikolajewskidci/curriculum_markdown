```js
// Destructuring Assignment
// The two most used data structures in JavaScript are Object and Array.

// Objects allow us to create a single entity that stores data items by key, and arrays allow us to gather data items into an ordered collection.

// But when we pass those to a function, it may need not an object/array as a whole, but rather individual pieces.

// Destructuring assignment is a special syntax that allows us to “unpack” arrays or objects into a bunch of variables, as sometimes that’s more convenient. Destructuring also works great with complex functions that have a lot of parameters, default values, and so on.


// Array destructuring
// How the array is destructured into variables:

// 1.
const arr = ["Ilya", "Kantor"]

// destructuring assignment
// sets firstName = arr[0]
// and surname = arr[1]
// const [firstName, surname] = arr; 
//          OR
const firstName = arr[0];
const surname = arr[1];

console.log(firstName); // Ilya
console.log(surname);   // Kantor

// It’s called “destructuring assignment,” because it “destructurizes” by copying items into variables. But the array itself is not modified.
console.log(arr);       // [ 'Ilya', 'Kantor' ]

// ---------##---------

// 2.
// if second element is not needed.
// the second element of the array is skipped, the third one is assigned to title, and the rest of the array items is also skipped (as there are no variables for them).
const [firstName2, , title] = ["Julius", "Caesar", "Consul", "of the Roman Republic"];

console.log(title); // Consul

// ---------##---------

// 3.
const [c, , e, f] = [44, 66, 88, 99]; // jump over 66 
console.log(c); // 44
console.log(e); // 88
console.log(f); // 99
// WE CAN EVEN SKIP NUMBERS / PARTS WE ARE NOT INTERESTED IN

// ---------##---------
// 4. 
// we can use it with any iterable, not only arrays:

const [var1, var2, var3] = "abc"; // ["a", "b", "c"]
console.log(var1);              // a
console.log(var2);              // b
console.log(var3);              // c
console.log(typeof var1)        // string

// ---------##---------
// 5.

const europeanCitiy = ['Paris', 'london'];
const asianCities = ['Shanghai', 'Tokyo'];
const twoArrays = [...europeanCitiy, ...asianCities]; // Destructuring
// We can access more than one on the right

console.log(twoArrays);     // [ 'Paris', 'London', 'Shanghai', 'Tokyo' ]

// ---------##---------
// 6.

// if we have a very long array 
const alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'];
// const letterA = alphabet[0];
// const letterB = alphabet[1];
// const letterF = alphabet[5];

// makes sense to shorten it like that (and its failsafer)
const [letterA, letterB, , , , letterF] = alphabet; // recommended for arrays 
console.log(letterA);
console.log(letterB);
console.log(letterF);

// ---------##---------
// Destructuring Objects
// 7.

const user = {};
[user.name, user.surname] = "Ilya Kantor".split(' ');

console.log(user.name);         // Ilya
console.log(user.surname);      // Kantor
console.log(user);              // { name: 'Ilya', surname: 'Kantor' }

// ---------##---------
// 8.
// Object destructuring must have same identifier

let i, j;   // "assignables"
({ i, j } = {
    i: 10,
    j: 20
});

// we produce individual variables i, j 

console.log(i);     // 10
console.log(j);     // 20

console.log(typeof i);      // number

// ---------##---------
// 9.

let k, l, m;
({ k, l, ...m } = {
    k: 10,
    l: 20,
    o: 40,
    p: 100
});
console.log(m);     // { o: 40, p: 100 }

// ---------##---------
// 10.

// Function without destructuring 
function easyFunction(array) {
    const num1 = array[0];
    const num2 = array[1];
    const num3 = array[2];
    const num4 = array[3];
    return (num1 + num2 + num3 + num4)
}
console.log(easyFunction([1, 2, 3, 4]));        // 10

// ---------##---------
// Destructuring in functions

function easyFunction(arr) {       // function without Destructuring
    const num1 = arr[0];
    const num2 = arr[1];
    const num3 = arr[2];
    const num4 = arr[3];

    return (num1 + num2 + num3 + num4);
}

console.log(easyFunction([1, 2, 3, 4]));    // 10


function destructureFunction(arr) {    // function with Destructuring
    const [num1, num2, num3, num4] = arr;

    return (num1 + num2 + num3 + num4);
}

console.log(destructureFunction([1, 2, 3, 4]));     // 10


function destructureFunction2([num1, num2, num3, num4]) {      // shorter function with Destructuring
    // unpacking with destructuring
    return (num1 + num2 + num3 + num4);
}

console.log(destructureFunction2([1, 2, 3, 4]));     // 10

// ---------##---------
// 12.

// REACT
const stateObject = {
    name: 'Martina',
    age: 36
};
// more common case, predefined property names need to be reused
function myReactFunction({ name, age }) {
    console.log(`My name is  ${name} and I am ${age} years old`);
}
myReactFunction(stateObject);   // My name is Martina and I'm 36 years old.
```