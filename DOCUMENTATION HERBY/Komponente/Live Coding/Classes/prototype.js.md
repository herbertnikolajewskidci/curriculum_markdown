Prototyp-Methoden sind Methoden, die Teil des Prototyps einer Klasse in JavaScript sind. Sie können verwendet werden, um Methoden für alle Instanzen einer Klasse bereitzustellen, anstatt für jede Instanz eine separate Kopie der Methode zu erstellen.

Mit anderen Worten sind sie Methoden, die einer Klasse oder einem Objekt **im nachhinein** zugewiesen werden und **allen Instanzen dieser Klasse** oder dieses Objekts gemeinsam zur Verfügung stehen. Diese Methoden werden als Teil des Prototyps des Objekts definiert und können von jeder Instanz aufgerufen werden.

Ein Vorteil von Prototyp-Methoden ist, dass sie nur einmal im Prototyp definiert werden müssen und dann von allen Instanzen verwendet werden können. Dies spart Speicher und macht es einfacher, Methoden zu ändern oder zu überschreiben.

Prototyp-Methoden können in JavaScript durch die Verwendung der Syntax `prototype.methodName = function() {...}` definiert werden. Hier ist ein Beispiel:

```JS
class Person {
  constructor(name) {
    this.name = name;
  }
}

Person.prototype.greet = function() {
  return `Hallo, ich bin ${this.name}`;
};

const person = new Person('Max');
console.log(person.greet()); // Hallo, ich bin Max
```

In diesem Beispiel haben wir eine Klasse `Person` definiert, die einen Namen als Parameter annimmt. Wir haben dann eine Prototyp-Methode `greet` hinzugefügt, die eine Begrüßungsnachricht ausgibt, die den Namen der Person enthält. Jede Instanz der Klasse `Person` hat automatisch Zugriff auf diese Methode.

Zur Vertiefung: https://www.youtube.com/watch?v=1UTqFAjYx1k