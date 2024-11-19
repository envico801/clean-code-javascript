========== Question ==========  

### Are you reducing conditionals in your code?

Understanding why and how to avoid excessive conditionals is crucial for writing maintainable code. While it may seem impossible to eliminate `if` statements entirely, polymorphism offers a powerful alternative that better adheres to the Single Responsibility Principle.

Key benefits of avoiding conditionals through polymorphism:

-   Better adherence to Single Responsibility Principle

-   Easier to test and maintain

-   More extensible code

-   Clearer class responsibilities

**Bad:**

```javascript
class Airplane {
    // ...
    getCruisingAltitude() {
        switch (this.type) {
            case '777':
                return this.getMaxAltitude() - this.getPassengerCount();
            case 'Air Force One':
                return this.getMaxAltitude();
            case 'Cessna':
                return this.getMaxAltitude() - this.getFuelExpenditure();
        }
    }
}
```  

========== Answer ==========  

By using inheritance and polymorphism, we can create specific classes for each airplane type, each implementing its own cruising altitude calculation. This approach makes the code more maintainable and easier to extend with new airplane types.

**Good:**

```javascript
class Airplane {
    // ...
}

class Boeing777 extends Airplane {
    // ...
    getCruisingAltitude() {
        return this.getMaxAltitude() - this.getPassengerCount();
    }
}

class AirForceOne extends Airplane {
    // ...
    getCruisingAltitude() {
        return this.getMaxAltitude();
    }
}

class Cessna extends Airplane {
    // ...
    getCruisingAltitude() {
        return this.getMaxAltitude() - this.getFuelExpenditure();
    }
}
```

========== Id ==========  
21

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#21-Are-you-reducing-conditionals-in-your-code

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
