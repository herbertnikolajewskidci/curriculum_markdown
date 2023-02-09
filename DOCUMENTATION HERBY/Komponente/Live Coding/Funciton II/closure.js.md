1.  Eine Funktion innerhalb einer Funktion ist eine Funktion, die innerhalb einer anderen Funktion definiert wird. Die <u>**innere Funktion**</u> kann auf **<u>Variablen</u>** und Funktionen der **<u>äußeren Funktion zugreifen</u>** und hat auch Zugriff auf ihre eigenen Variablen. Hier ist ein Beispiel:

```js
function outerFunction() {
    const x = 5;
    function innerFunction(y) {
        return x + y;
    }
    return innerFunction;
}
add_5 = outerFunction();
console.log(add_5(3)); // 8
```

2. Durch verschachtelte Scopes haben wir Zugriff auf Variablen, die in einem äußeren Scope definiert wurden, von einer Funktion innerhalb dieses Scopes. Hier ist ein Beispiel:

```js
function outerFunction() {
    const x = 5;
    function innerFunction(y) {
        return x + y;
    }
    return innerFunction;
}
add_5 = outerFunction();
console.log(add_5(3)); // 8
```

3. Kurze Definition: Closure wird als Funktion definiert, die mindestens eine Variable und einen verschachtelten Scope enthält. Hier ist ein Beispiel:

```js
function outerFunction() {
    const x = 5;
    function innerFunction(y) {
        return x + y;
    }
    return innerFunction;
}
add_5 = outerFunction();
console.log(add_5(3)); // 8
```

4.  Higher-Order-Funktionen sind Funktionen, die andere Funktionen zurückgeben. Hier ist ein Beispiel:

```js
function outerFunction() {
    const x = 5;
    function innerFunction(y) {
        return x + y;
    }
    return innerFunction;
}
add_5 = outerFunction();
console.log(add_5(3)); // 8
```

5. Die Funktionsaufruf-Zwiebel beschreibt, wie Funktionsaufrufe von innen nach außen vorgenommen werden. Jeder Funktionsaufruf bildet eine Schicht, die um den vorherigen Funktionsaufruf gelegt wird. Hier ist ein Beispiel:

```js
function outerFunction() {
    const x = 5;
    function innerFunction(y) {
        return x + y;
    }
    return innerFunction;
}
add_5 = outerFunction();
console.log(add_5(3)); // 8
```

In diesem Beispiel wird die äußere Funktion `outer_function` mit dem Argument `5` aufgerufen, dann wird die innere Funktion `inner_function`

---

**Defenition:** Ein Closure in JavaScript ist eine Funktion, die **<u>Zugang</u>** zu ihren eigenen Variablen und den Variablen ihrer **<u>äußeren Funktionen</u>** hat, auch wenn diese Funktionen bereits ausgeführt wurden und ihre Variablen normalerweise gelöscht worden wären. Ein Closure ermöglicht es, den **<u>Zustand</u>** und den **<u>Kontext</u>** einer Funktion zu speichern und zu **<u>überleben, nachdem die Funktion zurückgegeben</u>** wurde. Closures werden oft verwendet, um Funktionalität zu erstellen, die sich auf Daten bezieht, die **<u>außerhalb der Funktion definiert wurden.</u>**

```js
function outerFunction(x) {
    // Hier ist eine lokale Variable namens "counter"
    let counter = 0;

    // Hier ist eine innere Funktion, die Zugriff auf die lokale Variable "counter" hat
    function innerFunction() {
        counter += x;
        return counter;
    }

    // Rückgabe der inneren Funktion
    return innerFunction;
}

// Hier wird die äußere Funktion aufgerufen und das Ergebnis in einer Variablen gespeichert
const closure = outerFunction(5);

// Hier wird die gespeicherte innere Funktion aufgerufen
console.log(closure()); // Ausgabe: 5
console.log(closure()); // Ausgabe: 10
console.log(closure()); // Ausgabe: 15

// Hier wird die äußere Funktion erneut aufgerufen und das Ergebnis in einer neuen Variablen gespeichert
const anotherClosure = outerFunction(10);

// Hier wird die neu gespeicherte innere Funktion aufgerufen
console.log(anotherClosure()); // Ausgabe: 10
console.log(anotherClosure()); // Ausgabe: 20
```

Erklärung:

-   Ein Closure ist eine Funktion, die sich auf ihren Kontext (Lokale Variablen, Parameter usw.) "erinnert".
-   In diesem Beispiel erstellt die äußere Funktion `outerFunction` eine lokale Variable namens `counter` und eine innere Funktion namens `innerFunction`.
-   Die innere Funktion `innerFunction` hat Zugriff auf die lokale Variable `counter`, auch nachdem die äußere Funktion `outerFunction` bereits beendet wurde.
-   Wenn die äußere Funktion `outerFunction` aufgerufen wird, wird die innere Funktion `innerFunction` zurückgegeben.
-   Jedes Mal, wenn die zurückgegebene innere Funktion aufgerufen wird, hat sie Zugriff auf den aktuellen Wert der lokalen Variable `counter` und kann ihn ändern.
-   Da jeder Aufruf von `outerFunction` eine neue Instanz der inneren Funktion erzeugt, kann man mehrere unabhängige Closures erzeugen, die jeweils eigene Versionen der lokalen Variablen haben.

---

Weiteres Beispiel:

```js
function createCounter() {
    let count = 0;
    return function () {
        count++;
        return count;
    };
}

const counter1 = createCounter();
const counter2 = createCounter();

console.log(counter1()); // Ausgabe: 1
console.log(counter1()); // Ausgabe: 2
console.log(counter2()); // Ausgabe: 1
console.log(counter1()); // Ausgabe: 3
console.log(counter2()); // Ausgabe: 2
```

Erklärung:

-   In diesem Beispiel erstellt die Funktion `createCounter` eine lokale Variable `count` und eine innere Funktion, die den Wert von `count` um 1 erhöht und ihn zurückgibt.
-   Jeder Aufruf von `createCounter` erzeugt eine neue Instanz der inneren Funktion, die ihre eigene Version von `count` hat.
-   Da jede Instanz eine eigene Version von `count` hat, kann man mehrere unabhängige Counter erzeugen, indem man `createCounter` mehrere Male aufruft.

---

```js
function createGreeting(greeting) {
    return function (name) {
        return `${greeting}, ${name}!`;
    };
}

const sayHello = createGreeting("Hello");
const sayHi = createGreeting("Hi");

console.log(sayHello("John")); // Ausgabe: "Hello, John!"
console.log(sayHello("Jane")); // Ausgabe: "Hello, Jane!"
console.log(sayHi("Alex")); // Ausgabe: "Hi, Alex!"
console.log(sayHi("Anna")); // Ausgabe: "Hi, Anna!"
```

Erklärung:

-   In diesem Beispiel erstellt die Funktion `createGreeting` eine innere Funktion, die einen Gruß und einen Namen zu einer vollständigen Begrüßung zusammenfügt.
-   Die äußere Funktion `createGreeting` nimmt einen Gruß als Argument `greeting` entgegen und gibt eine innere Funktion zurück, die einen Namen als Argument `name` entgegen nimmt.
-   Jeder Aufruf von `createGreeting` erzeugt eine neue Instanz der inneren Funktion, die ihre eigene Version von `greeting` hat.
-   Da jede Instanz eine eigene Version von `greeting` hat, kann man mehrere unabhängige Greeter erzeugen, indem man `createGreeting` mehrere Male aufruft.

---

```js
function createAdder(x) {
    return function (y) {
        return x + y;
    };
}

const add5 = createAdder(5);
const add10 = createAdder(10);

console.log(add5(3)); // Ausgabe: 8
console.log(add5(7)); // Ausgabe: 12
console.log(add10(5)); // Ausgabe: 15
console.log(add10(2)); // Ausgabe: 12
```

Erklärung:

-   In diesem Beispiel erstellt die Funktion `createAdder` eine innere Funktion, die zwei Zahlen addiert.
-   Die äußere Funktion `createAdder` nimmt eine Zahl als Argument `x` entgegen und gibt eine innere Funktion zurück, die eine weitere Zahl als Argument `y` entgegen nimmt.
-   Jeder Aufruf von `createAdder` erzeugt eine neue Instanz der inneren Funktion, die ihre eigene Version von `x` hat.
-   Da jede Instanz eine eigene Version von `x` hat, kann man mehrere unabhängige Adder erzeugen, indem man `createAdder` mehrere Male aufruft.

#### Lexical Scope

Lexischer Scope in JavaScript bezieht sich auf die Art und Weise, wie Variablen und Funktionen Zugriff auf ihre Umgebung und äußere Scopes haben. In JavaScript wird der Zugriff auf Variablen und Funktionen durch ihre Definition im Code bestimmt, anstatt durch ihren Aufruf.

Ein Beispiel für lexischen Scope in JavaScript ist das Folgende:

```js
const outerVariable = "outer";

function outerFunction() {
    const innerVariable = "inner";

    function innerFunction() {
        console.log(outerVariable); // "outer"
        console.log(innerVariable); // "inner"
    }

    innerFunction();
}

outerFunction();
```

In diesem Beispiel hat die innere Funktion `innerFunction` Zugriff auf beide Variablen `outerVariable` und `innerVariable`, die in äußeren Scopes definiert wurden. Dies ist ein Beispiel für lexischen Scope, da der Zugriff auf diese Variablen durch ihre Definition im Code bestimmt wird, anstatt durch ihren Aufruf.

**Metapher:** Stell dir vor, du hast eine Schachtel, in der du verschiedene Dinge aufbewahren kannst. Diese Schachtel ist wie ein Bereich im Computer, in dem du Variablen und Funktionen aufbewahren kannst.

Jetzt stell dir vor, dass du eine zweite Schachtel hast, die in der ersten Schachtel versteckt ist. Diese zweite Schachtel kann auf die Dinge in der ersten Schachtel zugreifen, aber die erste Schachtel kann nicht auf die Dinge in der zweiten Schachtel zugreifen.

Das ist wie lexischer Scope im Computer. Es ist wie mehrere Schachteln, in denen du Variablen und Funktionen aufbewahren kannst. Jede Schachtel kann auf die Dinge in äußeren Schachteln zugreifen, aber äußere Schachteln können nicht auf die Dinge in inneren Schachteln zugreifen.
