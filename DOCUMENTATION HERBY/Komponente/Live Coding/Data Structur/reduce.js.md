```js
// https://javascript.info/array-methods

// The reduce() method executes a reducer function (that you provide) on each member of the array resulting in a single output value.

// When we need to iterate over an array – we can use forEach, for or for..of.

// When we need to iterate and return the data for each element – we can use map.

// The methods 'arr.reduce' and 'arr.reduceRight' are used to calculate a single value based on the array.

// The syntax is:

// const value = arr.reduce(function(previousValue, item, index, array) {
//   // ...
// }, initial);

// Your reducer function's returned value is assigned to the accumulator, 
// whose value is remembered across each iteration throughout the array and ultimately becomes the final, single resulting value.

const numbers = [1, 2, 3, 4];

const sumReducer = (accumulator, currentValue) => accumulator + currentValue;
const sum = numbers.reduce(sumReducer);
console.log(sum);   // 10

const sum2 = numbers.reduce(sumReducer, 5);

console.log(sum2);  // 15

// ------------------------------ //

const arr = [1, 2, 3, 4, 5];
const result = arr.reduce((sum, current) => sum + current, 10);   // 10 is the current value passed to the first callback
console.log(result); // 25

// ------------------------------ //

const reducer = function (accumulator, currentValue, currentIndex, array) {
  console.log("acc ", accumulator, "cv", currentValue, "ci", currentIndex, "arr ", array)
  return accumulator + currentValue;
}

arr.reduce(reducer);
```