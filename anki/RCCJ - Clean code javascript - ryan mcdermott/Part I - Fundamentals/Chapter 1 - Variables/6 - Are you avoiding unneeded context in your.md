========== Question ==========  

### Are you avoiding unneeded context in your names?

What's redundant about this code?

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

<details><summary>🔍 Hints</summary>

Think about:

-   What context does the `Car` object already provide?

-   Are the 'car' prefixes adding any valuable information?

-   How could we make this more concise while maintaining clarity?

</details>  

========== Answer ==========  

**The Principle**:

When the context is already clear from the class or object name, don't repeat it in the property names. This creates unnecessary verbosity and redundancy.

**Solution**:

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

**Why is this better?**

We've removed the redundant 'car' prefix from `car.carColor` since the `Car` object already provides that context. The code is more concise while remaining just as clear.

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
