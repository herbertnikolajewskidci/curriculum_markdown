```js
// Die Big O Notation ist eine Methode zur Schätzung der Laufzeitkomplexität eines Algorithmus. Sie gibt an, wie sich die benötigte Zeit mit der Größe der Eingabedaten erhöht. In Javascript kann man Big O verwenden, um die Effizienz von Funktionen zu bewerten.

//Ein paar Beispiele für Big O Notationen in Javascript sind:

// O(1) bedeutet, dass die Funktion unabhängig von der Größe der Eingabedaten immer gleich schnell ausgeführt wird.

function multiplayFirstAndLastElment(array) {
    return array[0] * array[array.length - 1];
}

// Diese Funktion liefert die Multiplaktion aus dem ersten und dem letzen Element eines Arrays. Egal wie groß das Array ist, es wird jeweils immer nur ein Zugriff auf das Array erforderlich sein, um das erste Element und das letzte Element abzurufen. Daher hat die Funktion eine Komplexität von O(1).

// O(n) bedeutet, dass die Funktion proportional zur Größe der Eingabedaten länger dauert.

function sumArray(array) {
    let total = 0;
    for (let i = 0; i < array.length; i++) {
        total += array[i];
    }
    return total;
}

// Diese Funktion berechnet die Summe aller Elemente eines Arrays. Die Zeit, die die Funktion benötigt, steigt proportional zur Größe des Arrays. Wenn das Array beispielsweise 10 Elemente hat, müssen 10 Schritte ausgeführt werden, um die Summe zu berechnen. Daher hat die Funktion eine Komplexität von O(n).

// O(n^2) bedeutet, dass die Funktion proportional zur Quadrat der Größe der Eingabedaten länger dauert.

function nestedLoop(array) {
    for (let i = 0; i < array.length; i++) {
        for (let j = 0; j < array.length; j++) {
            console.log(array[i], array[j]);
        }
    }
}

// Diese Funktion führt eine innere Schleife für jedes Element des Arrays aus. Daher muss jedes Element des Arrays für jedes andere Element des Arrays verarbeitet werden. Wenn das Array beispielsweise 10 Elemente hat, müssen insgesamt 100 Schritte ausgeführt werden. Daher hat die Funktion eine Komplexität von O(n^2).

// O(log n) Binäre Suche

const arr = [2, 5, 12, 36, 54, 75, 100];

function binarySearch(array, target) {
    let left = 0;
    let right = array.length - 1;
    while (left <= right) {
        let middle = Math.floor((left + right) / 2); // <== Überall wo ein Problem in 2 hälften geteilt wird, haben wir in aller regel O(log n)
        console.log("left", left, "middle", middle, "right", right);
        if (array[middle] === target) {
            return middle;
        } else if (array[middle] < target) {
            left = middle + 1;
        } else {
            right = middle - 1;
        }
    }
    return -1;
}

console.log(binarySearch(arr, 12));

// Dies ist eine Implementierung einer binären Suche, die eine gesuchte Zahl in einem sortierten Array findet. Bei jedem Schritt der Schleife wird das Suchintervall halbiert, daher wird die Zeit, die die Funktion benötigt, logarithmisch zur Größe des Arrays steigen. Daher hat die Funktion eine Komplexität von O(log n).
// Telefonbuch Beispiel -> https://www.youtube.com/watch?v=DSffdCT5Cx4

```


![Big O Complexity chart](https://paper-attachments.dropbox.com/s_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664885448372_Untitled.drawio+17.png)

Zur Vertiefung: https://www.youtube.com/embed/3yUuo7TqMW8