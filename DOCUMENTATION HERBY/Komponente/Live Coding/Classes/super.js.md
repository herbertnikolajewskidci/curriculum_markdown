`super` in einer JavaScript-Klasse bezieht sich auf die übergeordnete Klasse, die mit dem `extends`-Schlüsselwort erweitert wurde. Es ermöglicht den Zugriff auf die Methoden und Eigenschaften der übergeordneten Klasse.

Hier ist ein Beispiel, das `super` verwendet, um die Methode der übergeordneten Klasse aufzurufen:

```JS
class Animal {
  constructor(name) {
    this.name = name;
  }

  sayHello() {
    return `Hello, I'm ${this.name}`;
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  sayHello() {
    return `${super.sayHello()}, I'm a ${this.breed}`;
  }
}

const myDog = new Dog("Rufus", "Golden Retriever");
console.log(myDog.sayHello()); // "Hello, I'm Rufus, I'm a Golden Retriever"
```

In diesem Beispiel erweitert die `Dog`-Klasse die `Animal`-Klasse. Wenn wir eine Instanz der `Dog`-Klasse erstellen, wird zuerst der Konstruktor der übergeordneten Klasse aufgerufen (`super(name)`), um den Namen des Tieres zu setzen. Anschließend wird dann der Konstruktor der `Dog`-Klasse aufgerufen, um die Rasse zu setzen.

In der `sayHello`-Methode der `Dog`-Klasse wird `super.sayHello()` aufgerufen, um die gleichnamige Methode der `Animal`-Klasse aufzurufen und dann den Rückgabewert anzupassen, um auch die Rasse des Hundes anzugeben.