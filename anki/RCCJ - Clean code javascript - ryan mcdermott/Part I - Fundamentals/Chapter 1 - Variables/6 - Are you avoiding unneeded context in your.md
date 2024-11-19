========== Question ==========  

### Are you avoiding unneeded context in your names?

When the context is already clear from the class or object name, don't repeat it in the property names. This creates unnecessary verbosity and redundancy.

**Bad:**

```javascript
const Car = {
    carMake: 'Honda',
    carModel: 'Accord',
    carColor: 'Blue',
};

function paintCar(car, color) {
    car.carColor = color;
}
```  

========== Answer ==========  

Remove redundant context when the parent object/class name already provides it. This makes the code more concise and easier to read while maintaining clarity.

**Good:**

```javascript
const Car = {
    make: 'Honda',
    model: 'Accord',
    color: 'Blue',
};

function paintCar(car, color) {
    car.color = color;
}
```

========== Id ==========  
6

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#6-Are-you-avoiding-unneeded-context-in-your

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
