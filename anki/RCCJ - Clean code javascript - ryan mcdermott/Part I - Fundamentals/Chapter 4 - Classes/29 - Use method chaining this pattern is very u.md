========== Question ==========  

### Use method chaining

This pattern is very useful in JavaScript and you see it in many libraries such

as jQuery and Lodash. It allows your code to be expressive, and less verbose.

For that reason, I say, use method chaining and take a look at how clean your code

will be. In your class functions, simply return `this` at the end of every function,

and you can chain further class methods onto it.

**Bad:**

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
car.save();
```  

========== Answer ==========  

**Good:**

```javascript
class Car {
    constructor(make, model, color) {
        this.make = make;
        this.model = model;
        this.color = color;
    }
    setMake(make) {
        this.make = make;
        // NOTE: Returning this for chaining
        return this;
    }
    setModel(model) {
        this.model = model;
        // NOTE: Returning this for chaining
        return this;
    }
    setColor(color) {
        this.color = color;
        // NOTE: Returning this for chaining
        return this;
    }
    save() {
        console.log(this.make, this.model, this.color);
        // NOTE: Returning this for chaining
        return this;
    }
}
const car = new Car('Ford', 'F-150', 'red').setColor('pink').save();
```

========== Id ==========  
29

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 4 - Classes

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-4-Classes::#29-Use-method-chaining-this-pattern-is-very-u

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
