========== Question ==========  

### Are you preferring ES2015/ES6 classes over ES5 functions?

Look at this code. What's wrong with it?

```javascript
const Animal = function (age) {
    if (!(this instanceof Animal)) {
        throw new Error('Instantiate Animal with `new`');
    }
    this.age = age;
};

Animal.prototype.move = function move() {};

const Mammal = function (age, furColor) {
    if (!(this instanceof Mammal)) {
        throw new Error('Instantiate Mammal with `new`');
    }
    Animal.call(this, age);
    this.furColor = furColor;
};

Mammal.prototype = Object.create(Animal.prototype);
Mammal.prototype.constructor = Mammal;
Mammal.prototype.liveBirth = function liveBirth() {};

const Human = function (age, furColor, languageSpoken) {
    if (!(this instanceof Human)) {
        throw new Error('Instantiate Human with `new`');
    }

    Mammal.call(this, age, furColor);
    this.languageSpoken = languageSpoken;
};

Human.prototype = Object.create(Mammal.prototype);
Human.prototype.constructor = Human;
Human.prototype.speak = function speak() {};
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   How readable is this inheritance pattern?

-   How much boilerplate code is needed?

-   Is there a clearer way to show the relationship between classes?

-   What happens if you forget the `new` keyword?

</details>  

========== Answer ==========  

**The Principle**:

ES2015/ES6 classes provide a clearer, more intuitive syntax for object-oriented programming in JavaScript compared to the ES5 prototype-based approach. They make inheritance patterns more readable and reduce boilerplate code.

Key benefits of ES6 classes:

-   Clearer syntax for OOP concepts

-   Built-in constructor method

-   Straightforward inheritance with 'extends'

-   Better handling of `this` binding

-   Enhanced readability and maintainability

**Solution**:

```javascript
class Animal {
    constructor(age) {
        this.age = age;
    }

    move() {
        /* ... */
    }
}

class Mammal extends Animal {
    constructor(age, furColor) {
        super(age);
        this.furColor = furColor;
    }

    liveBirth() {
        /* ... */
    }
}

class Human extends Mammal {
    constructor(age, furColor, languageSpoken) {
        super(age, furColor);
        this.languageSpoken = languageSpoken;
    }

    speak() {
        /* ... */
    }
}
```

**Why is this better?**

-   Clearer inheritance relationships

-   Less boilerplate code

-   Built-in constructor method

-   No manual prototype chain setup

-   More familiar to developers from other languages

========== Id ==========  
28

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 4 - Classes

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-4-Classes::#28-Are-you-preferring-es2015-es6-classes-over

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
