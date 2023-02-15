# callbacks

## Einleitung

In JavaScript sind **Callbacks Funktionen,** die als **Argumente an andere Funktionen übergeben** werden und von diesen Funktionen aufgerufen werden, wenn bestimmte Ereignisse oder Bedingungen eintreten. Callbacks sind ein wichtiger Bestandteil der asynchronen Programmierung in JavaScript und werden häufig in Verbindung mit Array-Methoden, Timer-Funktionen oder Ereignissen verwendet.

Callbacks ermöglichen es, dass Funktionen unabhängig voneinander ausgeführt werden können, ohne dass der Codeblock wartet, bis eine Funktion abgeschlossen ist. Dies ist besonders nützlich, wenn es darum geht, asynchrone Operationen auszuführen, wie das Laden von Daten aus einer API oder das Ausführen einer Funktion nach einer bestimmten Zeit.

In diesem Kontext ermöglichen Callbacks es, dass Sie Code schreiben können, der effizienter ausgeführt wird und gleichzeitig einfacher zu lesen und zu verwalten ist.

---

## Beispiele für Callback Functions

1.  **Array-Methoden:** Viele Array-Methoden in JavaScript akzeptieren Callbacks, um bestimmte Funktionalitäten zu implementieren. Ein gutes Beispiel ist die `.forEach()`-Methode. Hier ist ein Beispiel:

```js
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function (number) {
    console.log(number);
});

// Output:
// 1
// 2
// 3
// 4
// 5
```

In diesem Beispiel übergibt die `.forEach()`-Methode jeden Wert des Arrays an die Callback-Funktion, die als Argument übergeben wird.

---

2.  **setTimeout():** Die `setTimeout()`-Funktion akzeptiert auch Callbacks, um bestimmte Funktionalitäten nach einer bestimmten Zeit auszuführen. Hier ist ein Beispiel:

```js
setTimeout(function () {
    console.log("Hello, World!");
}, 1000);

// Output:
// Hello, World! (nach einer Sekunde)
```

In diesem Beispiel ruft die `setTimeout()`-Funktion nach einer Sekunde die Callback-Funktion auf, um die Meldung "Hello, World!" auszugeben.

---

3.  **Array.sort():** Die `.sort()`-Methode von JavaScript-Arrays kann auch Callbacks akzeptieren, um die Sortierreihenfolge zu definieren. Hier ist ein Beispiel:

```js
const names = ["John", "Jane", "Jim", "Jack"];

names.sort(function (a, b) {
    if (a < b) {
        return -1;
    }
    if (a > b) {
        return 1;
    }
    return 0;
});

console.log(names);

// Output:
// [ 'Jack', 'Jane', 'Jim', 'John' ]
```

In diesem Beispiel definiert die Callback-Funktion die Sortierreihenfolge der Elemente im Array.

Diese Beispiele zeigen, wie Callbacks in JavaScript verwendet werden können, um bestimmte Funktionalitäten auszuführen.

---

4. **Benutzerdefinierte Funktionen:** Sie können auch Callbacks in benutzerdefinierten Funktionen verwenden, um bestimmte Funktionalitäten auszuführen. Hier ist ein Beispiel:

```js
function doSomething(callback) {
    console.log("Doing something...");
    callback();
}

doSomething(function () {
    console.log("Done!");
});

// Output:
// Doing something...
// Done!
```

---

### Eigene forEach-Methode

Hier ist ein einfaches Beispiel für eine benutzerdefinierte Funktion, die die gleiche Funktionalität wie die `.forEach()`-Methode hat:

```js
function myForEach(array, callback) {
    for (let i = 0; i < array.length; i++) {
        callback(array[i]);
    }
}

const numbers = [1, 2, 3, 4, 5];

myForEach(numbers, function (number) {
    console.log(number);
});

// Output:
// 1
// 2
// 3
// 4
// 5
```

In diesem Beispiel wird eine benutzerdefinierte Funktion `myForEach()` erstellt, die ein Array und eine Callback-Funktion als Argumente akzeptiert. Die Funktion iteriert über jedes Element im Array und übergibt jedes Element an die Callback-Funktion. Die Callback-Funktion verarbeitet dann jedes Element.

Diese benutzerdefinierte Funktion hat dieselbe Funktionalität wie die `.forEach()`-Methode und kann ebenfalls verwendet werden, um jedes Element eines Arrays zu durchlaufen und zu verarbeiten.

---

### Eigene Map-Methode

Hier ist ein einfaches Beispiel für eine benutzerdefinierte Funktion, die die gleiche Funktionalität wie die `.map()`-Methode hat:

```js
function myMap(array, callback) {
    let transformedArray = [];
    for (let i = 0; i < array.length; i++) {
        transformedArray.push(callback(array[i]));
    }
    return transformedArray;
}

const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = myMap(numbers, (number) => number * 2);

console.log(doubledNumbers);

// Output:
// [2, 4, 6, 8, 10]
```

In diesem Beispiel wird eine benutzerdefinierte Funktion `myMap()` erstellt, die ein Array und eine Callback-Funktion als Argumente akzeptiert. Die Funktion iteriert über jedes Element im Array und übergibt jedes Element an die Callback-Funktion. Die Callback-Funktion verarbeitet dann jedes Element und gibt das Ergebnis zurück, das in einem neuen Array gespeichert wird.

Diese benutzerdefinierte Funktion hat dieselbe Funktionalität wie die `.map()`-Methode und kann ebenfalls verwendet werden, um jedes Element eines Arrays zu transformieren.
