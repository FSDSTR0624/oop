# Object-oriented Programming (OOP)

En informática, una clase es una plantilla para la creación de objetos de datos según un modelo predefinido. Las clases se utilizan para representar entidades o conceptos, como los sustantivos en el lenguaje. Cada clase es un modelo que define un conjunto de variables —el estado—, y métodos apropiados para operar con dichos datos —el comportamiento—.

## La sintaxis “class”

Si hemos comentado que una clase es una plantilla para la creación de objetos, entonces podemos definir la clase de la siguiente manera:

```javascript
class Car {
  color: "red";
}
```

Entonces usamos `new MyClass()` para crear un objeto nuevo.

```javascript
const car1 = new Car();
```

Una vez creado el objeto, podemos acceder a sus propiedades como hemos hecho siempre:

```javascript
console.log(car1.color);
```

### constructor

Si por alguna razón queremos definir unas variables dentro de la clase, debemos usar el método `constructor`

```javascript
class Car {
  constructor(owner, ico) {
    this.kms = 0;
    this.fuel = 100;
    this.owner = owner;
    this.ico = ico;
  }
}
```

### las clases permiten añadir métodos adicionales al objeto

```javascript
class Car {
  constructor(owner, ico) {
    this.kms = 0;
    this.fuel = 100;
    this.owner = owner;
    this.ico = ico;
    this.openedTrunk = false;
  }

  openTrunk() {
    this.openedTrunk = true;
  }
}
```

Cuando se llama a `new User("John")`:

- Un objeto nuevo es creado.
- El constructor se ejecuta con el argumento dado y lo asigna a `this.name`.

…Entonces podemos llamar a sus métodos, como `user.sayHi()`.

> [!WARNING] > **No va una coma entre métodos de clase**
> Un tropiezo común en desarrolladores principiantes es poner una coma entre los métodos de clase, lo que resulta en un error de sintaxis.
> La notación aquí no debe ser confundida con la sintaxis de objeto literal. Dentro de la clase no se requieren comas.

## Getters/setters

Al igual que los objetos literales, las clases pueden incluir getters/setters, propiedades calculadas, etc.

Aquí hay un ejemplo de user.name, implementado usando get/set:

```javascript
class Car {
  constructor(owner, ico) {
    this.kms = 0;
    this.fuel = 100;
    this.owner = owner;
    this.ico = ico;
    this.openedTrunk = false;
  }

  get owner() {
    return "Mi nombre es " + this._owner;
  }

  // Setter method for the owner property
  set owner(value) {
    if (value.length < 4) {
      alert("Nombre demasiado corto.");
      return;
    }
    this._owner = value;
  }

  openDoor() {
    this.openedTrunk = true;
  }
}

let car1 = new Car("Pepe", "🚗");
alert(car.owner); // Mi nombre es Pepe

car2 = new Car(""); // Nombre demasiado corto.
```
