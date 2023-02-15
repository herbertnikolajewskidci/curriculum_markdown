# Klassen

## Einleitung

Klassen sind ein wichtiger Bestandteil des objektorientierten Programmierens (OOP). Sie stellen eine Möglichkeit dar, Daten und Verhaltensweisen zu gruppieren und wiederverwendbar zu machen. In JavaScript können wir mit Klassen eigene Typen definieren, die wir dann zum Erstellen von Instanzen verwenden können.

---

## Date Klasse

Die Klasse "Date" in JavaScript stellt einen Standardtyp bereit, mit dem wir Datums- und Uhrzeitinformationen verwalten können. Hier ist ein Beispiel, wie wir eine Instanz der Klasse "Date" erstellen und darauf zugreifen können:

```js
const date = new Date();
console.log(date.getFullYear()); // Ausgabe: das aktuelle Jahr
console.log(date.getMonth()); // Ausgabe: der aktuelle Monat (0-11)
console.log(date.getDate()); // Ausgabe: das aktuelle Datum
```

Wie wir sehen, können wir eine Instanz einer Klasse erstellen, indem wir das Schlüsselwort **"new"** verwenden und die **Klasse aufrufen,** gefolgt von einer Liste von Argumenten in Klammern. Anschließend können wir auf die Methoden und Eigenschaften der Instanz über den Punktoperator (.) zugreifen.

---

## Objekt und Klassen

Klassen und Objekte in JavaScript haben eng miteinander zu tun, da **Klassen** dazu verwendet werden, **Objekte zu erstellen.** Eine Klasse ist eine Art **Vorlage oder Schablone,** die das Verhalten und die Eigenschaften eines bestimmten Typs von **Objekten** definiert. Wenn wir eine Klasse definieren, können wir Instanzen dieser Klasse erstellen, die tatsächliche Objekte sind.

Jedes Objekt, das wir in JavaScript erstellen, hat einen **bestimmten Typ,** entweder einen Standardtyp (z. B. Number, String, Array) oder einen Benutzerdefinierten Typ, der durch eine Klasse definiert wird. Jede Instanz einer Klasse besitzt eine **eigene Kopie der Eigenschaften und Methoden,** die von der Klasse definiert werden, aber alle haben **dieselben Verhaltensweisen** und können **dieselben Methoden aufrufen.**

Zusammenfassend können wir sagen, dass Klassen in JavaScript eine Möglichkeit darstellen, benutzerdefinierte Typen von Objekten zu erstellen und zu verwalten. Jede Instanz einer Klasse ist ein tatsächliches Objekt, das seine eigene Kopie der Eigenschaften und Methoden besitzt, die von der Klasse definiert werden.

```JS
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    return `Hallo, ich bin ${this.name} und ich bin ${this.age} Jahre alt.`;
  }
}

const person1 = new Person("John Doe", 30);
const person2 = new Person("Jane Doe", 25);

console.log(person1.sayHello()); 
// Ausgabe: Hallo, ich bin John Doe und ich bin 30 Jahre alt.

console.log(person2.sayHello()); 
// Ausgabe: Hallo, ich bin Jane Doe und ich bin 25 Jahre alt.
```

Wir definieren hier die Klasse `Person`, die zwei Eigenschaften `name` und `age` und eine Methode `sayHello()` besitzt. Die Methode `constructor` wird aufgerufen, wenn wir eine neue Instanz der Klasse `Person` erstellen, und ermöglicht es uns, die Eigenschaften `name` und `age` zu initialisieren.

Anschließend erstellen wir zwei Instanzen der Klasse `Person`, `person1` und `person2`, und geben die Rückgabewerte der Methode `sayHello()` auf der Konsole aus. Wie man sieht, ist jede Instanz ein eigenständiges Objekt mit eigenen Eigenschaften und Methoden.

---

### constructor methode

In JavaScript kann eine Klasse eine `constructor`-Methode haben, die bei der Erstellung einer neuen Instanz dieser Klasse automatisch aufgerufen wird. Die `constructor`-Methode kann verwendet werden, um die Anfangswerte für die Eigenschaften einer Instanz zu setzen oder andere Initialisierungsaufgaben durchzuführen.

Das `constructor`-Schlüsselwort ist ein besonderes Schlüsselwort in JavaScript und kann nur einmal pro Klasse verwendet werden. Hier ist ein Beispiel:

```JS
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    return `Hallo, ich bin ${this.name} und ich bin ${this.age} Jahre alt.`;
  }
}
```

Wenn wir eine neue Instanz der Klasse `Person` erstellen, wird die `constructor`-Methode automatisch aufgerufen und nimmt die Argumente `name` und `age` entgegen. Diese Argumente werden verwendet, um die Eigenschaften `this.name` und `this.age` zu initialisieren.

Hier ist ein Beispiel, wie wir eine Instanz der Klasse `Person` erstellen und die `constructor`-Methode aufrufen:

```js
const person1 = new Person("John Doe", 30);
```

In diesem Beispiel wird die `constructor`-Methode mit den Argumenten `"John Doe"` und `30` aufgerufen. Die Eigenschaften `this.name` und `this.age` werden mit den Werten `"John Doe"` und `30` initialisiert.

### this

Das Schlüsselwort `this` in einer Klasse verweist auf die aktuelle Instanz der Klasse. Innerhalb einer Methode einer Klasse bezieht sich `this` auf die aktuelle Instanz, auf die die Methode aufgerufen wird. Innerhalb einer `constructor`-Methode bezieht sich `this` auf die neu erstellte Instanz der Klasse.

Wenn Wir die Eigenschaften einer Klasseninstanz initialisieren möchten, können Sie die `constructor`-Methode verwenden und die `this`-Schlüsselwort verwenden, um auf die aktuelle Instanz der Klasse zu verweisen. Hier ist ein Beispiel:

```JS
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person("John Doe", 30);
console.log(person1.name); // "John Doe"
console.log(person1.age); // 30
```

In diesem Beispiel wird die `constructor`-Methode verwendet, um die Eigenschaften `name` und `age` einer neuen Instanz der Klasse `Person` zu initialisieren. Das `this`-Schlüsselwort verweist auf die aktuelle Instanz der Klasse, die wir durch den Konstruktoraufruf erstellt haben.

Es ist wichtig zu beachten, dass das `this`-Schlüsselwort erst bekannt ist, wenn die Klassenmethode aufgerufen wird. Bevor die Methode aufgerufen wird, hat das `this`-Schlüsselwort keine Bedeutung. Außerdem ist es wichtig zu beachten, dass das `this`-Schlüsselwort in JavaScript nicht absolut ist und je nach Kontext unterschiedlich interpretiert werden kann.

### Kontext von this

In JavaScript wird das `this`-Schlüsselwort dynamisch und basierend auf dem Kontext bestimmt, in dem es verwendet wird. Das bedeutet, dass `this` unterschiedliche Werte haben kann, je nach Kontext, in dem es verwendet wird.

#### Innerhalb einer Methode einer Klasse:

Im Kontext einer Klassenmethode bezieht sich `this` auf die aktuelle Instanz der Klasse, auf die die Methode aufgerufen wird. Hier ist ein Beispiel:

```JS
class Person {
  constructor(name) {
    this.name = name;
  }

  sayName() {
    console.log(this.name);
  }
}

const person1 = new Person("John Doe");
person1.sayName(); // "John Doe"
```

In diesem Beispiel bezieht sich `this` innerhalb der `sayName`-Methode auf die aktuelle Instanz der Klasse `Person`, die über den Konstruktoraufruf `new Person("John Doe")` erstellt wurde.

#### Innerhalb einer regulären Funktion:

Wenn Sie das `this`-Schlüsselwort jedoch in einem regulären Funktionskontext verwenden, bezieht es sich auf das globale Objekt (`window` im Browser, `global` im Node.js). Hier ist ein Beispiel:

```JS
const name = "Global Name";

function sayName() {
  console.log(this.name);
}

sayName(); // undefined
```

Hier sind weitere Kontexte, in denen das `this`-Schlüsselwort unterschiedlich interpretiert wird:

#### Mit dem `call`, `apply` oder `bind`-Methoden:
Diese Methoden können verwendet werden, um den Kontext einer Funktion zu ändern, indem sie ein bestimmtes Objekt als Kontext für das `this`-Schlüsselwort festlegen.

```JS
const obj = {
  name: 'Objekt',
};

function greet(greeting) {
  return `${greeting}, ich bin ${this.name}`;
}

// Verwendung der call-Methode
console.log(greet.call(obj, 'Hallo')); // Hallo, ich bin Objekt

// Verwendung der apply-Methode
console.log(greet.apply(obj, ['Hallo'])); // Hallo, ich bin Objekt

// Verwendung der bind-Methode
const boundGreet = greet.bind(obj);
console.log(boundGreet('Hallo')); // Hallo, ich bin Objekt
```

In diesem Beispiel definieren wir ein einfaches Objekt mit dem Namen `obj` und eine Funktion `greet`, die einen Gruß ausgibt. Wir verwenden dann die `call`, `apply` und `bind`-Methoden, um den Kontext für die Funktion `greet` auf das Objekt `obj` zu setzen.

Die `call`-Methode erwartet als erstes Argument das Objekt, das als Kontext verwendet werden soll, und die weiteren Argumente werden direkt an die Funktion übergeben.

Die `apply`-Methode funktioniert ähnlich wie die `call`-Methode, aber es erwartet die Argumente in Form eines Arrays anstatt als einzelne Argumente.

Die `bind`-Methode dient dazu, eine neue Funktion zu erzeugen, die einen festen Kontext hat. In unserem Beispiel erzeugen wir eine neue Funktion `boundGreet`, die an den Kontext `obj` gebunden ist. Jedes Mal, wenn `boundGreet` aufgerufen wird, wird es den gleichen Kontext verwenden.

#### Innerhalb einer Arrow-Funktion:
Innerhalb einer Arrow-Funktion bezieht sich `this` auf den Kontext, in dem die Funktion definiert wurde und nicht auf den Kontext, in dem sie ausgeführt wurde.

```JS
const obj = {
  name: 'Objekt',
  greet: () => {
    return `Hallo, ich bin ${this.name}`;
  },
};

console.log(obj.greet()); // Hallo, ich bin undefined
```

In diesem Beispiel definieren wir ein Objekt mit dem Namen `obj`, das eine Arrow-Funktion `greet` enthält. Wenn wir die Funktion `greet` aufrufen, bezieht sich `this` auf den Kontext, in dem die Funktion definiert wurde, und nicht auf den Kontext, in dem sie ausgeführt wurde. Da die Funktion `greet` innerhalb des Objekts `obj` definiert ist, bezieht sich `this` auf das globale Objekt und nicht auf `obj`. Daher ist der Wert für `this.name` `undefined`.

Um den gewünschten Kontext für `this` zu erzielen, kann die Funktion `greet` als reguläre Funktion statt als Arrow-Funktion definiert werden:

```JS
const obj = {
  name: 'Objekt',
  greet: function () {
    return `Hallo, ich bin ${this.name}`;
  },
};

console.log(obj.greet()); // Hallo, ich bin Objekt
```

Jetzt bezieht sich `this` auf das Objekt `obj`, und der Wert für `this.name` ist `'Objekt'`.

#### Beispiel mit Arrow Function als Callback Function

```JS
const obj2 = {
    name: "Anton",
    arr: [1, 2, 3, 4],
    greet: function () {
        this.arr.forEach(() => {
            console.log(`Hallo, ich bin ${this.name}`);
        });
    },
};

obj2.greet()

// Output:
// Hallo, ich bin Anton
// Hallo, ich bin Anton
// Hallo, ich bin Anton
// Hallo, ich bin Anton
```

In diesem Beispiel ist der Kontext innerhalb der Arrow Function innerhalb der forEach Methode das obj2-Objekt, weil die Arrow Function den Kontext des äußeren Kontexts beibehält. Daher wird `this.name` als `"Anton"` ausgewertet und es wird `"Hallo, ich bin Anton"` ausgegeben. Wenn wir eine reguläre Funktion anstelle einer Arrow Function innerhalb der forEach Methode verwenden, würde der Kontext der Funktion `undefined` sein und `this.name` würde als `undefined` ausgewertet.

---

## Fazit

Zusammenfassend kann man sagen, dass Klassen in JavaScript eine praktische Möglichkeit sind, um komplexe Objekte zu erstellen und zu organisieren. Eine Klasse definiert eine Vorlage für die Erstellung von Objekten und verwendet den Konstruktor, um Instanzen dieser Klasse zu initialisieren. Der Konstruktor ist eine besondere Methode innerhalb einer Klasse, die bei der Instanziierung eines Objekts automatisch aufgerufen wird.

Das Schlüsselwort `this` innerhalb einer Klasse oder einer Methode bezieht sich auf die aktuelle Instanz des Objekts, das die Methode aufruft. Je nach Kontext, in dem eine Methode aufgerufen wird, kann der Kontext für `this` unterschiedlich interpretiert werden. In regulären Funktionen bezieht sich `this` auf den Kontext, in dem die Funktion aufgerufen wurde, während `this` in Arrow-Funktionen auf den Kontext verweist, in dem die Funktion definiert wurde.

Um den Kontext für `this` in regulären Funktionen beizubehalten, können Methoden wie `call`, `apply` oder `bind` verwendet werden. Mit diesen Methoden kann der Kontext für `this` explizit festgelegt werden.

