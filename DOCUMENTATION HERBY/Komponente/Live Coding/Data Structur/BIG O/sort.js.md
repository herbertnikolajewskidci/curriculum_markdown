## lexikografische Sortierung (So wie wir es bisher kennengelernt haben)

```js
const numbers = [30, 1, 4, 10, 5, 9, 2, 6, 500, 3, 50];

numbers.sort();
console.log(numbers);
// Output: [1, 10, 2, 3, 30, 4, 5, 50, 500, 6, 9]
```

In diesem Beispiel wird ein Array mit Zahlen erstellt und die `sort()` Methode aufgerufen. Die Methode sortiert die Zahlen im Array in aufsteigender lexikografischer Reihenfolge.

## numerische Sortierung

```js
const numbers = [30, 1, 4, 10, 5, 9, 2, 6, 500, 3, 50];

numbers.sort(function (a, b) {
    return a - b;
});
console.log(numbers);
// Output: [1, 2, 3, 4, 5, 6, 9, 10, 30, 50, 500]
```

In diesem Beispiel wird ein Array mit Zahlen erstellt und die `sort()` Methode mit einer benutzerdefinierten Sortierfunktion aufgerufen. Die Funktion vergleicht die aktuellen Werte `a` und `b` und gibt `a - b` zurück. Wenn das Ergebnis kleiner als Null ist, wird `a` vor `b` sortiert, wenn es größer als Null ist, wird `b` vor `a` sortiert.

**Das geht auch mit Strings:**

```js
const words = ["apple", "banana", "cherry", "date"];

// Sortierung nach Länge der Wörter
words.sort(function (a, b) {
    return a.length - b.length;
});
console.log(words);
// Output: ['date', 'apple', 'banana', 'cherry']
```

Die anonyme Callback-Funktion im obigen Beispiel wird in der Regel auch als `compareFn` bezeichnet.

### compareFn

Die `sort()` Methode in JavaScript akzeptiert eine Vergleichsfunktion (`compareFn`), die verwendet wird, um zwei Elemente im Array miteinander zu vergleichen und zu bestimmen, in welcher Reihenfolge sie sortiert werden sollen. Hier ist ein Beispiel:

```js
const numbers = [30, 1, 4, 10, 5, 9, 2, 6, 500, 3, 50];

numbers.sort(function compareFn(a, b) {
    // Rückgabewert kleiner als 0: a wird vor b platziert
    // Rückgabewert gleich 0: a und b bleiben unverändert
    // Rückgabewert größer als 0: b wird vor a platziert
    return a - b;
});
console.log(numbers);
// Output: [1, 2, 3, 4, 5, 6, 9, 10, 30, 50, 500]
```

In diesem Beispiel wird die Vergleichsfunktion `compareFn` verwendet, um die Zahlen im Array `numbers` in numerischer Reihenfolge zu sortieren. Die Funktion vergleicht dabei jeweils zwei Elemente `a` und `b` im Array und gibt einen Wert zurück, der angibt, in welcher Reihenfolge sie sortiert werden sollen.

---

## Sortierung von Objekten

In JavaScript kann man das Array von Objekten mit der `sort()` Methode sortieren, indem man eine benutzerdefinierte Vergleichsfunktion an die Methode übergibt. Hier ist ein Beispiel:

### Sortierung nach dem Alter

```js
const employees = [
    { name: "John", age: 32 },
    { name: "Jane", age: 27 },
    { name: "Bob", age: 45 },
    { name: "Alice", age: 36 },
];

employees.sort(function compareFn(a, b) {
    // Rückgabewert kleiner als 0: a wird vor b platziert
    // Rückgabewert gleich 0: a und b bleiben unverändert
    // Rückgabewert größer als 0: b wird vor a platziert
    return a.age - b.age;
});
console.log(employees);
// Output: [
//   { name: "Jane", age: 27 },
//   { name: "John", age: 32 },
//   { name: "Alice", age: 36 },
//   { name: "Bob", age: 45 },
// ]
```

In diesem Beispiel wird die Vergleichsfunktion `compareFn` verwendet, um das Array `employees` nach dem Alter der Mitarbeiter zu sortieren. Die Funktion vergleicht dabei jeweils zwei Elemente `a` und `b` im Array und gibt einen Wert zurück, der angibt, in welcher Reihenfolge sie sortiert werden sollen.

### Sortierung nach dem Namen

Um das Array von Objekten `employees` nach dem Namen zu sortieren, kann man eine Vergleichsfunktion an die `sort()` Methode übergeben, die die Namen der Objekte vergleicht. Hier ist ein Beispiel:

```js
const employees = [
    { name: "John", age: 32 },
    { name: "Jane", age: 27 },
    { name: "Bob", age: 45 },
    { name: "Alice", age: 36 },
];

employees.sort(function compareFn(a, b) {
    // Rückgabewert kleiner als 0: a wird vor b platziert
    // Rückgabewert gleich 0: a und b bleiben unverändert
    // Rückgabewert größer als 0: b wird vor a platziert
    if (a.name < b.name) {
        return -1;
    }
    if (a.name > b.name) {
        return 1;
    }
    return 0;
});
console.log(employees);
// Output: [
//   { name: "Alice", age: 36 },
//   { name: "Bob", age: 45 },
//   { name: "Jane", age: 27 },
//   { name: "John", age: 32 },
// ]
```

In diesem Beispiel wird die Vergleichsfunktion `compareFn` verwendet, um das Array `employees` nach den Namen der Mitarbeiter zu sortieren. Die Funktion vergleicht dabei jeweils zwei Elemente `a` und `b` im Array und gibt einen Wert zurück, der angibt, in welcher Reihenfolge sie sortiert werden sollen.

---

## Big O von sort()

Die Big O Notation der `sort()` Methode in JavaScript hängt von der Implementierung des sortierenden Algorithmus ab, der von den verschiedenen JavaScript-Implementierungen unterschiedlich sein kann.

Die meisten JavaScript-Implementierungen nutzen entweder den Quick-Sort-Algorithmus oder eine Variante des Merge-Sort-Algorithmus.

Quick-Sort hat eine Durchschnitts-Zeitkomplexität von O(n log n), aber in einigen schlechten Fällen kann es auch O(n^2) erreichen.

Merge-Sort hat eine Zeitkomplexität von O(n log n) in allen Fällen.

Es ist also sicher zu sagen, dass die Big O Notation der `sort()` Methode in JavaScript mindestens O(n log n) ist.

Die `sort()` Methode in JavaScript nutzt in der Regel einen Timsort-Algorithmus, um Arrays zu sortieren. Timsort ist ein hybrider Algorithmus, der Teile von Insertion-Sort und Merge-Sort nutzt.

Wenn Sie jedoch eine bestimmte Art der Sortierung benötigen, können Sie die `sort()` Methode mit einer Vergleichsfunktion überschreiben. Hier ist ein Beispiel, wie Sie das Array `employees` nach dem Namen sortieren können:

```js
const employees = [
    { name: "John", age: 28 },
    { name: "Jane", age: 32 },
    { name: "Jim", age: 40 },
];

employees.sort(function (a, b) {
    let nameA = a.name.toUpperCase();
    let nameB = b.name.toUpperCase();

    if (nameA < nameB) {
        return -1;
    }
    if (nameA > nameB) {
        return 1;
    }

    return 0;
});

console.log(employees);
// Output: [{ name: "Jim", age: 40 }, { name: "Jane", age: 32 }, { name: "John", age: 28 }]
```

In diesem Beispiel wird die `sort()` Methode mit einer Vergleichsfunktion überschrieben, die den Namen des Objekts in Großbuchstaben umwandelt und dann die Vergleichsergebnisse zurückgibt, um das Array zu sortieren.

### Appendix (Falls es dich interessiert)

Hier ist ein Beispiel einer Implementation des **Quick-Sort-Algorithmus** in JavaScript:

```js
function quickSort(array) {
    if (array.length <= 1) {
        return array;
    }

    let pivot = array[array.length - 1];
    let left = [];
    let right = [];

    for (let i = 0; i < array.length - 1; i++) {
        if (array[i] < pivot) {
            left.push(array[i]);
        } else {
            right.push(array[i]);
        }
    }

    return quickSort(left).concat([pivot], quickSort(right));
}

let array = [5, 3, 7, 6, 2, 1, 4];
console.log(quickSort(array));
// Output: [1, 2, 3, 4, 5, 6, 7]
```

In diesem Beispiel wird der Quick-Sort-Algorithmus rekursiv aufgerufen, um das Array zu sortieren. Zuerst wird das letzte Element des Arrays als Pivot-Element ausgewählt. Dann werden alle Elemente, die kleiner als das Pivot-Element sind, in einem linken Array gespeichert, und alle Elemente, die größer oder gleich dem Pivot-Element sind, in einem rechten Array gespeichert. Die Funktion wird dann rekursiv für beide Arrays aufgerufen, bis alle Elemente sortiert sind.

---

Hier ist ein Beispiel einer Implementation des **Merge-Sort-Algorithmus** in JavaScript:

```js
function mergeSort(array) {
    if (array.length <= 1) {
        return array;
    }

    let mid = Math.floor(array.length / 2);
    let left = array.slice(0, mid);
    let right = array.slice(mid);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    let result = [];
    let i = 0;
    let j = 0;

    while (i < left.length && j < right.length) {
        if (left[i] < right[j]) {
            result.push(left[i++]);
        } else {
            result.push(right[j++]);
        }
    }

    while (i < left.length) {
        result.push(left[i++]);
    }

    while (j < right.length) {
        result.push(right[j++]);
    }

    return result;
}

let array = [5, 3, 7, 6, 2, 1, 4];
console.log(mergeSort(array));
// Output: [1, 2, 3, 4, 5, 6, 7]
```

In diesem Beispiel wird der Merge-Sort-Algorithmus rekursiv aufgerufen, um das Array zu sortieren. Die Funktion `mergeSort` teilt das Array in zwei Hälften und sortiert jede Hälfte rekursiv. Die Funktion `merge` führt dann die beiden sortierten Hälften zu einem einzigen sortierten Array zusammen.
