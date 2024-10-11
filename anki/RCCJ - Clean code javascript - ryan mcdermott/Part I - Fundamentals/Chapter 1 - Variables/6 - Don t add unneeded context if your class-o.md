========== Question ==========  

### Don't add unneeded context

If your class/object name tells you something, don't repeat that in your

variable name.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#6-Don-t-add-unneeded-context-if-your-class-o

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
