========== Question ==========  

### Are you using method chaining for fluent interfaces?

Look at this code. What's wrong with it?

```javascript
class Car {
    constructor(make, model, color) {
        this.make = make;
        this.model = model;
        this.color = color;
    }

    setMake(make) {
        this.make = make;
    }

    setModel(model) {
        this.model = model;
    }

    setColor(color) {
        this.color = color;
    }

    save() {
        console.log(this.make, this.model, this.color);
    }
}

const car = new Car('Ford', 'F-150', 'red');
car.setColor('pink');
car.setModel('Mustang');
car.save();
```

<details><summary>🔍 Hints</summary>

Think about:

-   How many lines of code are needed to modify the car?

-   Is there a way to make this more fluent?

-   What do popular libraries like jQuery do?

-   What needs to be returned from each method?

</details>  

========== Answer ==========  

**The Principle**:

Method chaining is a pattern that allows multiple methods to be called in a single statement, making code more fluent and expressive. This pattern is commonly seen in libraries like jQuery and Lodash.

Key benefits of method chaining:

-   More readable and expressive code

-   Reduced variable declarations

-   Fluent interface

-   Compact syntax

-   Better code flow

**Solution**:

```javascript
class Car {
    constructor(make, model, color) {
        this.make = make;
        this.model = model;
        this.color = color;
    }

    setMake(make) {
        this.make = make;
        return this; // Enable chaining
    }

    setModel(model) {
        this.model = model;
        return this; // Enable chaining
    }

    setColor(color) {
        this.color = color;
        return this; // Enable chaining
    }

    save() {
        console.log(this.make, this.model, this.color);
        return this; // Enable chaining
    }
}

const car = new Car('Ford', 'F-150', 'red')
    .setColor('pink')
    .setModel('Mustang')
    .save();
```

**Why is this better?**

-   More fluent and readable

-   Fewer lines of code

-   More expressive API

-   Enables operation chaining

-   Follows builder pattern principles

========== Id ==========  
29

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 4 - Classes

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-4-Classes::#29-Are-you-using-method-chaining-for-fluent-i

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
