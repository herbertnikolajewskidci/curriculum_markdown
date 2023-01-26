```JavaScript
// NESTED LOOP (VERSCHACHTELTE SCHLEIFE)

// LOOP INSIDE LOOP (SCHLEIFE IN DER SCHLEIFE )

const num = 3;

for(let i = 0; i <= num; i++){
  
  for(let j = 0; j <= num; j++){
    
    console.log(i, j);
    
  }
}

// 0 0
// 0 1
// 0 2
// 0 3
// 1 0
// 1 1
// 1 2
// 1 3
// 2 0
// 2 1
// 2 2
// 2 3
// 3 0
// 3 1
// 3 2
// 3 3

// ---------##---------

const num2 = 3;
const x = 5;

for (let i = 0; i <= num2; i++) {       // äußerer loop 
    console.log("outer loop i = ", i);
    for(let j = 0; j <= x; j++) {       // verschachtelter loop // innerer loop
        console.log("Inner loop j = ", j);
        console.log("outer loop i = ", i);  // den äußeren Zähler können wir verwenden, wegen des Block-Scopes
    }
    
}

// outer loop i =  0
// Inner loop j =  0
// outer loop i =  0
// Inner loop j =  1
// outer loop i =  0
// Inner loop j =  2
// outer loop i =  0
// Inner loop j =  3
// outer loop i =  0
// Inner loop j =  4
// outer loop i =  0
// Inner loop j =  5
// outer loop i =  0
// outer loop i =  1
// Inner loop j =  0
// outer loop i =  1
// Inner loop j =  1
// outer loop i =  1
// Inner loop j =  2
// outer loop i =  1
// Inner loop j =  3
// outer loop i =  1
// Inner loop j =  4
// outer loop i =  1
// Inner loop j =  5
// outer loop i =  1
// outer loop i =  2
// Inner loop j =  0
// outer loop i =  2
// Inner loop j =  1
// outer loop i =  2
// Inner loop j =  2
// outer loop i =  2
// Inner loop j =  3
// outer loop i =  2
// Inner loop j =  4
// outer loop i =  2
// Inner loop j =  5
// outer loop i =  2
// outer loop i =  3
// Inner loop j =  0
// outer loop i =  3
// Inner loop j =  1
// outer loop i =  3
// Inner loop j =  2
// outer loop i =  3
// Inner loop j =  3
// outer loop i =  3
// Inner loop j =  4
// outer loop i =  3
// Inner loop j =  5
// outer loop i =  3

for (let i = 0; i < 5; i++) { // outer loop 
    // index, iterator, counter
    for (let j = 0; j < 5; j++) { // nested loop 
        // would it work? 
        console.log('j', j); 
    }
    console.log('i', i);

}

// j 0
// j 1
// j 2
// j 3
// j 4
// i 0
// j 0
// j 1
// j 2
// j 3
// j 4
// i 1
// j 0
// j 1
// j 2
// j 3
// j 4
// i 2
// j 0
// j 1
// j 2
// j 3
// j 4
// i 3
// j 0
// j 1
// j 2
// j 3
// j 4
// i 4

//--------##---------

const normalArray = ["a", "b", "c", "d", "e"]; // length = 5

// verschachtelte arrays 
// Manchmal müssen wir mit Arrays innerhalb von Arrays arbeiten
const arrayInsideOfAnArray = [
    [1, 2, 1, 24], // [0]
    [8, 11, 9, 4],
    [7, 0, 7, 27],
    [7, 4, 28, 14], // ignored
    [3, 10, 26, 7] // innerLength = 4
]; // length = 5 
// wie können wir auf das normale Array zugreifen
console.log(normalArray[0]); // first item

console.log(arrayInsideOfAnArray[0]); // erstes Element des verschachtelten Arrays
console.log(arrayInsideOfAnArray[4]); // letztes Element des verschachtelten Arrays
//  [i][j] 
console.log(arrayInsideOfAnArray[0][0]); // allererste verschachtelte Position 
console.log(arrayInsideOfAnArray.length);


for (let i = 0; i < arrayInsideOfAnArray.length; i++) {
    // in dem äußeren Array
    console.log(arrayInsideOfAnArray[i]); // 5 times 
    // die ganze Zeile erhalten

    for (let j = 0; j < arrayInsideOfAnArray[i].length; j++) {
        // in dem inneren Array  
        if(i !== 3) { // die vierte Zeile ignorieren
            console.log(arrayInsideOfAnArray[i][j]); // 20 times = 5 * 4
            // jeden einzelnen Element erhalten
        }   
    }
}
```