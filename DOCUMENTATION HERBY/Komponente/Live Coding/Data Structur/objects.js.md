```js

// Ein JavaScript-Objekt ist eine durch Kommata getrennte Liste von Name-Wert-Paaren, die in geschweifte Klammern eingeschlossen sind.
// Objekte kapseln Daten ein und schließen sie in ein geordnetes Paket ein. Dadurch wird die Verwendung globaler Variablen minimiert,
// die beim Kombinieren von Code Probleme verursachen können.

const user = {        // an object
    name: "John",   // bei key "name" speichere value "John"
    age: 30,        // bei key "age" speichere value 30
};

// Die letzte Eigenschaft in der Liste kann mit einem Komma enden. Dies wird als "TRAILING"- oder "HANGING"-Komma bezeichnet.
// Es erleichtert das Hinzufügen/Entfernen/Verschieben von Eigenschaften, weil alle Zeilen gleich gestaltet sind.

// Punktnotation
user.isAdmin = true;
console.log(user);  // { name: 'John', age: 30, isAdmin: true }

// Objekte sind veränderbar
delete user.age;
console.log(user);  // { name: 'John', isAdmin: true }


const user2 = {
    name: "John",
    age: 30,
    "likes birds": true  // multi word property name must be quoted
};

// Klammerschreibweise
// Bei Eigenschaften, die aus mehreren Wörtern bestehen, funktioniert der Punktzugriff nicht: user.likes birds = true

const user3 = {};

// set
user3["likes birds"] = true;

// get
console.log(user3);  // { 'likes birds': true }

// delete
delete user3["likes birds"];

console.log(user3); // {}

// ----------------//---------------- //
// Wir können eckige Klammern in einem Objekt verwenden. Das nennt man COMPUTED PROPERTIES.

const fruit = "kiwi";

const fruitBucket = {
    [fruit] : 5,
}

console.log(fruitBucket); // { kiwi: 5 }

// ODER

const fruits = 'apple';
const bag = {
  [fruits + 'Computers']: 5 // bag.appleComputers = 5
};

// ---------##---------
// Reservierte Wörter sind als Eigenschaftsnamen erlaubt

const obj = {
    for: 1,
    const: 2,
    return: 3
  };
  
  console.log(obj.for + obj.const + obj.return); // 6

// ---------##---------
// Objects vergleichen:

const personA = {       // verschachteltes Objekt
  name: {
      first_name: "John",
      last_name: "Doe"
  },
  age: 32,
  address: {
      strNum: 55,
      strName: "Abc",
      pinCode: 12334,
      country: "Germany"
  },
  companiesWorkedWith: {
      name: "dci",
      duration: "2years",
      year: 2023,
  }
};

console.log(personA.address.country);                // Germany
console.log(personA.companiesWorkedWith.year);       // 2013

const personB = {       // verschachteltes Objekt
  name: {
      first_name: "John",
      last_name: "Doe"
  },
  age: 32,
  address: {
      strNum: 55,
      strName: "Abc",
      pinCode: 12334,
      country: "Germany"
  },
  companiesWorkedWith: {
      name: "dci",
      duration: "2years",
      year: 2023,
  }
};
```
### Hier weiter
```js
// Finde eine Funktion in lodash, die beim Vergleich der beiden Objekte true zurückgibt
console.log(personA === personB);   // false

console.log(personA.age === personB.age);    // true

// ---------##---------
// In echtem Code verwenden wir oft vorhandene Variablen als Werte für Eigenschaftsnamen.

// Property value shorthand
// Die Eigenschaften bekommen die gleichen Namen wie Variablen. Der Anwendungsfall, eine Eigenschaft aus einer Variablen zu machen, ist sehr häufig,
// sodass es eine spezielle Abkürzung für Eigenschaftswerte gibt, um sie zu verkürzen.
// Anstelle von name:name können wir einfach name schreiben, etwa so:

function createUser(name, age) {
  return {        // Property value shorthand
      name,       // same as name: name
      age         // same as age: age
  };
}

const user4 = createUser("John", 30);     // calling function createUser and passing arguments

console.log(user4);     // { name: 'John', age: 30 }
console.log(user4.name);    // John

const user5 = createUser("Ketty", 66);    // calling function createUser and passing different arguments
console.log(user5);         // { name: 'Ketty', age: 66 }

// ---------##---------
// Prüfung des Vorhandenseins einer Eigenschaft, "in"-Operator
// Eine bemerkenswerte Eigenschaft von Objekten in JavaScript im Vergleich zu vielen anderen Sprachen ist, dass es möglich ist, auf jede Eigenschaft zuzugreifen.
// Es wird kein Fehler auftreten, wenn die Eigenschaft nicht existiert!
// Das Auslesen einer nicht existierenden Eigenschaft gibt einfach undefiniert zurück. Wir können also einfach testen, ob die Eigenschaft existiert:

const useR2 = { name: "John", age: 30 };

console.log(useR2.noSuchProperty === undefined);    // true

// Dafür gibt es auch einen speziellen Operator "in".
// Die Syntax lautet:   "Schlüssel" in object

console.log("age" in useR2);
console.log("blabla" in user);

// ---------##---------

// Object.keys()
// Die Methode Object.keys() gibt ein Array der aufzählbaren Eigenschaftsnamen eines bestimmten Objekts zurück,
// das in der gleichen Reihenfolge wie eine normale Schleife durchlaufen wird.

const personC = {       // nested object
  name: {
      first_name: "John",
      last_name: "Doe"
  },
  age: 32,
  address: {
      strNum: 55,
      strName: "Abc",
      pinCode: 12334,
      country: "Germany"
  },
  companiesWorkedWith: {
      name: "dci",
      duration: "2years",
      year: 2023,
  }
};

console.log(Object.keys(personC));  // [ 'name', 'age', 'address', 'companiesWorkedWith' ]

// Zugriff auf die Schlüssel des verschachtelten Objekts namens address:
console.log(Object.keys(personC.address));  // [ 'strNum', 'strName', 'pinCode', 'country' ]


// ---------##---------
// Object.values()
// Die Methode Object.values() gibt ein Array mit den aufzählbaren Eigenschaftswerten eines bestimmten Objekts zurück

console.log(Object.values(personC));

// [
//     { first_name: 'John', last_name: 'Doe' },
//     32,
//     { strNum: 55, strName: 'Abc', pinCode: 12334, country: 'Germany' },
//     { name: 'dci', duration: '2years', year: 2023, }
// ]

// accessing the values of the nested object called address:
console.log(Object.values(personC.address));    // [ 55, 'Abc', 12334, 'Germany' ]

// ---------##---------
// Object.entries erstellt ein Array von Arrays. Jedes innere Array hat zwei Elemente. Das erste Element ist die Eigenschaft, das zweite Element ist der Wert.

const entries = Object.entries(fruits)
console.log(entries)
// [
//   [apple, 28],
//   [orange, 17],
//   [pear, 54]
// ]

// Wenn wir Object.entries verwenden, sollten wir das Array in seine Schlüssel und Eigenschaften zerlegen.

for (const [fruit, count] of entries) {
    console.log(`There are ${count} ${fruit}s`)
}
  
  // Result
  // There are 28 apples
  // There are 17 oranges
  // There are 54 pears


// ---------##---------
// const user = {
//     name: "John",
//     age: 30,
//     isAdmin: true
//   };
  
//   for (const key in user) {
//     // keys
//     alert( key );  // name, age, isAdmin
//     // values for the keys
//     alert( user[key] ); // John, 30, true
//   }

```

