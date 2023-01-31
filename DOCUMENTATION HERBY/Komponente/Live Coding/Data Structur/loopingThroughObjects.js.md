```JavaScript
// Die for/in-Anweisung durchläuft die Eigenschaften eines Objekts in einer Schleife.
// Der Codeblock innerhalb der Schleife wird für jede Eigenschaft einmal ausgeführt.

// Verwenden Sie die for/in-Anweisung nicht zum Durchlaufen von Arrays, bei denen die Reihenfolge der Indizes wichtig ist.
// Verwenden Sie for...in, um über die Eigenschaften eines Objekts zu iterieren


const oldCar = {
  marke: 'Toyota',
  model: 'Tercel',
  year: '1996'
};

for (const key in oldCar) {
  console.log(`${key} --> ${oldCar[key]}`);
}

// marke --> Toyota
// modell --> Tercel

// --------------------------------------------------------- //

const person = {
    fname: "John", 
    lname: "Doe", 
    age:25
}; 

let text = "";
let x; // Eine Variable, die über die Eigenschaften eines Objekts iteriert
for (x in Person) {
  text = `${text} ${person[x]}`; // text += person[x] + " ";
  console.log(person[x]);
  
}

console.log(text);

// ----------##----------

// Sie können auch for...in verwenden, um über die Indexwerte einer Iterablen wie einem String/Array/Objekt zu iterieren:

const str = 'Blättern Sie die Seite um';

for (const index in str) {
  console.log(`Index von ${str[index]}: ${index}`);
}

// Index von B: 0
// Index von l: 1

// ----------##----------

const fruits = {
    äpfel: 28,
    orangen: 17,
    birnen: 54,
  }

const entries = Object.entries(fruits)
console.log(entries);                       
// [ [ 'äpfel', 28 ], [ 'orangen', 17 ], [ 'birnen', 54 ] ]

const keys = Object.keys(fruits)
for (const key of keys) {
  console.log(key)
}
// äpfel
// orangen
// birnen


for (const [fruit, count] of entries) {
    console.log(`Es gibt ${count} ${fruit}`)
}

// Es gibt 28 äpfel
// Es gibt 17 orangen
// Es gibt 54 birnen


// --------------------------------------------------------- //

// for...of verwenden, um über die Werte in einer Iterable zu iterieren

const animals = ['🐔', '🐷', '🐑', '🐇'];
const names = ['Gertrude', 'Henry', 'Melvin', 'Billy Bob'];

for (const animal of animals) {
  // Zufälliger Name für unser Tier
  const nameIdx = Math.floor(Math.random() * names.length);

  console.log(`${names[nameIdx]} the ${animal}`);
}


// Melvin the 🐔.
// Henry the 🐷.
// Henry the 🐑.
// Henry the 🐇
```

