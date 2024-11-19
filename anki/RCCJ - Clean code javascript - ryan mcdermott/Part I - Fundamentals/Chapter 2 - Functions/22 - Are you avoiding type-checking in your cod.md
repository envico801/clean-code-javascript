========== Question ==========  

### Are you avoiding type-checking in your code? (Part 1)

Type checking in JavaScript often indicates a design that could be improved through better abstraction and consistent interfaces. Instead of checking types, design your objects to support a common interface.

Key principles:

-   Use consistent interfaces across related objects

-   Leverage polymorphism instead of type checking

-   Design for behavior rather than type

**Bad:**

```javascript
function travelToTexas(vehicle) {
    if (vehicle instanceof Bicycle) {
        vehicle.pedal(this.currentLocation, new Location('texas'));
    } else if (vehicle instanceof Car) {
        vehicle.drive(this.currentLocation, new Location('texas'));
    }
}
```  

========== Answer ==========  

By implementing a common interface (move) across all vehicle types, we eliminate the need for type checking and create more maintainable, flexible code.

**Good:**

```javascript
function travelToTexas(vehicle) {
    vehicle.move(this.currentLocation, new Location('texas'));
}
```

========== Id ==========  
22

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#22-Are-you-avoiding-type-checking-in-your-cod

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
