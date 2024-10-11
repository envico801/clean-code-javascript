========== Question ==========  

### Avoid type-checking (part 1)

JavaScript is untyped, which means your functions can take any type of argument.

Sometimes you are bitten by this freedom and it becomes tempting to do

type-checking in your functions. There are many ways to avoid having to do this.

The first thing to consider is consistent APIs.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#22-Avoid-type-checking-part-1-javascript-is

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
