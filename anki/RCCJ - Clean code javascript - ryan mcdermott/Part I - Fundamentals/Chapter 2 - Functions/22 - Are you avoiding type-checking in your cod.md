========== Question ==========  

### Are you avoiding type-checking in your code? (Part 1)

Look at this code. What's wrong with it?

```javascript
function travelToTexas(vehicle) {
    if (vehicle instanceof Bicycle) {
        vehicle.pedal(this.currentLocation, new Location('texas'));
    } else if (vehicle instanceof Car) {
        vehicle.drive(this.currentLocation, new Location('texas'));
    }
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   How many vehicle types might we need to handle in the future?

-   What happens when we add a new vehicle type?

-   Is there a way to make this more flexible?

-   What common action are all vehicles performing?

</details>  

========== Answer ==========  

**The Principle**:

Type checking in JavaScript often indicates a design that could be improved through better abstraction and consistent interfaces. Instead of checking types, design your objects to support a common interface.

Key principles:

-   Use consistent interfaces across related objects

-   Leverage polymorphism instead of type checking

-   Design for behavior rather than type

**Solution**:

```javascript
function travelToTexas(vehicle) {
    vehicle.move(this.currentLocation, new Location('texas'));
}
```

**Why is this better?**

-   Each vehicle type implements a common `move` method

-   No need to modify this function when adding new vehicle types

-   Cleaner, more maintainable code

-   Better follows object-oriented principles

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
