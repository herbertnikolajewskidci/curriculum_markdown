In JavaScript gibt es ein Konzept namens "Class inheritance", bei dem man eine neue Klasse von einer bereits bestehenden Klasse erstellen kann. Hierfür wird das Schlüsselwort `extends` verwendet.

Mit `extends` kann eine neue Klasse eine bereits bestehende Klasse erweitern, wodurch die neue Klasse Zugriff auf alle öffentlichen und geschützten Eigenschaften und Methoden der ursprünglichen Klasse erhält. Die neue Klasse kann dann die bereits bestehenden Methoden überschreiben oder eigene Methoden hinzufügen.

Dies ist eine wichtige Funktionalität, da es ermöglicht, Code wiederzuverwenden und Verantwortungen aufzuteilen, was die Entwicklung von Anwendungen beschleunigt und vereinfacht.

```JS
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    return `Hallo, ich bin ${this.name} und ich bin ${this.age} Jahre alt.`;
  }
}

class Student extends Person {
  constructor(name, age, major) {
    super(name, age);
    this.major = major;
  }
  greet() {
    return `${super.greet()} Ich studiere ${this.major}.`;
  }
}

const student = new Student("Anna", 25, "Informatik");
console.log(student.greet());
// Ausgabe: Hallo, ich bin Anna und ich bin 25 Jahre alt. Ich studiere Informatik.
```

In diesem Beispiel erstellen wir eine Basisklasse `Person` mit einem Konstruktor und einer Methode `greet`. Anschließend erstellen wir eine erweiterte Klasse `Student`, die von `Person` erbt und eine eigene Methode `greet` hat. Die erweiterte Klasse verwendet dabei auch die Methode `greet` aus der Basisklasse mit `super.greet()`.

Zur Vertiefung: https://www.youtube.com/watch?v=jnME98ckDbQ 