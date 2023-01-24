```js
// Eine Methode ist eine als Eigenschaft gespeicherte Funktion.

// Objektmethoden werden direkt auf den Objektkonstruktor angewendet und verwenden die Objektinstanz als Parameter. Dies wird als statische Methode bezeichnet.

const newObj = {
    hallo: "Welt",
    123: 456,
    myFunction: function () { // Methode
        console.log("Hallo Welt!");
    }
};

console.log(neuesObj[123]); // 456

newObj.myFunction(); // Hallo Welt!

// ---------##---------

// Objekt // Funktion aufgerufen max.... => "METHODE" 
Math.max(1, 2, 3); // => REAL LIFE EXAMPLE
Math.min(1, 2, 3); // viele Mathe-Methoden in einem Objekt zur gleichen Zeit! 

// ---------##---------

const objectLiteral = {
    property: "hello world",
    key: "Dumplings",
    method: function () {
        console.log("Guten Morgen " + this.key);
    }
};

objectLiteral.method(); // Guten Morgen Knödel!

// ---------##---------
const marcelsLibrary = {
    sayHello: function () {
        console.log('Hallo Marcel');
    },
    sayGoodbye: function () {
        console.log('Auf Wiedersehen Marcel');
    }
}
marcelsLibrary.sayHello(); // Hallo Marcel
marcelsLibrary.sayGoodbye(); // Auf Wiedersehen Marcel

// hier sehen wir nur die Definitionen der Methoden
console.log(marcelsLibrary); // { sayHello: [Funktion: sayHello], sayGoodbye: [Funktion: sayGoodbye] }

// Methoden befinden sich darin, rufen Sie sie einzeln auf
console.log(Math); // Objekt [Math] {}        

// ---------##---------

const personOne = {
    name: "John",
    dateOfBirth: 2000,
    age(dateOfBirth) {
        const today = new Date();
        const year = heute.getFullYear();
        const age = year - dateOfBirth;
        return `${Alter}`;
    }
}

personOne.age(); // 19

// ---------##---------
// dies

const user = {
    Name: "John",
    age: 30,
    sayHi() {
        return this.name // um auf das Objekt zuzugreifen, kann eine Methode das Schlüsselwort 'this' verwenden. 
    }
}

// Der Wert von 'this' ist das Objekt VOR DEM PUNKT, das zum Aufruf der Methode sayHi verwendet wird.
// Ausführung von user.sayHi(), der Wert von 'this' wird user sein:
console.log(user.sayHi()); // John

// ---------##---------

const person = {
    firstName: "John",
    lastName: "Doe",
    id: 5566,
    fullName() {
        return `${this.firstName} ${this.lastName}`;
    }
};
console.log(person.fullName()); // John Doe

// ---------##---------

const user2 = {
    Name: "John",
    age: 30,
    sayHi() {
        return this.name // um auf das Objekt zuzugreifen, kann eine Methode das Schlüsselwort "this" verwenden. 
    }
};

console.log(user2); // { name: 'John', alter: 30, sayHi: [Funktion: sayHi] }

const admin = user2;

user2 = null; // Der Bezeichner user2 bezieht sich jetzt auf null.

console.log(user2); // null
console.log(admin); // { name: 'John', alter: 30, sayHi: [Function: sayHi] }

// der Wert von 'this' wird während der Laufzeit kontextabhängig ausgewertet
console.log(admin.sayHi()); // John

console.log(admin); // { name: 'John', alter: 30, sayHi: [Function: sayHi] }

// -------------##------------

const user3 = {
    Name: "John",
    age: 30,
};

const newRef = user3;

user3 = null;

console.log(user3); // null
console.log(newRef); // { Name: 'John', Alter: 30 }

// newRef = null;

console.log(newRef); // { Name: 'John', Alter: 30 }

// Garbage Collectors kommen zur Rettung.

// ---------##---------

// Andere Methoden, die wir bereits verwendet haben
// console.log;
// Math.max;
// String.prototype.toLowerCase;
// String.prototype.includes;
// Number.prototype.toFixed;
// Boolean.prototype.valueOf;
// Array.prototype.join;
// Object.prototype.hasOwnProperty;

// ---------##---------

// Object.keys()
// Object.values()
// Object.entries()
// Object.assign()
// Objekt.einfrieren()
// Object.seal()
// Object.getPrototypeOf()
// Object.create()
```