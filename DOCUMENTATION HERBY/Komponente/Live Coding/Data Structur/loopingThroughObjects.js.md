```JavaScript
// Die for/in-Anweisung durchläuft die Eigenschaften eines Objekts in einer Schleife.
// Der Codeblock innerhalb der Schleife wird für jede Eigenschaft einmal ausgeführt.

// Verwenden Sie die for/in-Anweisung nicht zum Durchlaufen von Arrays, bei denen die Reihenfolge der Indizes wichtig ist.
// Verwenden Sie for...in, um über die Eigenschaften eines Objekts zu iterieren


const oldCar = {
  Marke: 'Toyota',
  model: 'Tercel',
  year: '1996'
};

for (const key in oldCar) {
  console.log(`${key} --> ${oldCar[key]}`);
}

// Marke --> Toyota
// Modell --> Tercel

// --------------------------------------------------------- //

const person = {
    fname: "John", 
    lname: "Doe", 
    Alter:25
}; 

let text = "";
let x; // Eine Variable, die über die Eigenschaften eines Objekts iteriert
for (x in Person) {
  text = `${text}${person[x]}`; // text += person[x] + " ";
  console.log(person[x]);
  
}

console.log(text);

// ----------##----------

// Sie können auch for...in verwenden, um über die Indexwerte einer Iterablen wie einem String/Array/Objekt zu iterieren:

const str = 'Blättern Sie die Seite um';

for (const index in str) {
  console.log(`Index von ${str[index]}: ${index}`);
}

// Index von T: 0
// Index von u: 1

// ----------##----------

const fruits = {
    Apfel: 28,
    orange: 17,
    birne: 54,
  }

const entries = Object.entries(fruits)
console.log(entries);                       
// [ [ 'Apfel', 28 ], [ 'Orange', 17 ], [ 'Birne', 54 ] ]

const keys = Object.keys(fruits)
for (const key of keys) {
  console.log(key)
}
// Apfel
// Orange
// birne


for (const [fruit, count] of entries) {
    console.log(`Es gibt ${count} ${fruit}s`)
}

// Es gibt 28 Äpfel
// Es gibt 17 Orangen
// Es gibt 54 Birnen


// --------------------------------------------------------- //

// for...of verwenden, um über die Werte in einer Iterable zu iterieren

const animals = ['🐔', '🐷', '🐑', '🐇'];
const names = ['Gertrude', 'Henry', 'Melvin', 'Billy Bob'];

for (const animal of animals) {
  // Zufälliger Name für unser Tier
  const nameIdx = Math.floor(Math.random() * names.length);

  console.log(`${names[nameIdx]} the ${animal}`);
}


// Melvin der 🐔.
// Henry der 🐷.
// Henry der 🐑.
// Henry der 🐇
// adnaans-macbo
```
*** Übersetzt mit www.DeepL.com/Translator (kostenlose Version) ***

