========== Question ==========  

### Are you reducing conditionals in your code?

Look at this airplane code. What design issues do you see?

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

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens when you need to add a new airplane type?

-   How many places would you need to modify?

-   Is this following the Open/Closed Principle?

-   How could inheritance help here?

</details>  

========== Answer ==========  

**The Principle**:

Understanding why and how to avoid excessive conditionals is crucial for writing maintainable code. While it may seem impossible to eliminate `if` statements entirely, polymorphism offers a powerful alternative that better adheres to the Single Responsibility Principle.

Key benefits of avoiding conditionals through polymorphism:

-   Better adherence to Single Responsibility Principle

-   Easier to test and maintain

-   More extensible code

-   Clearer class responsibilities

**Solution**:

Here's a better approach using polymorphism:

```javascript
class Airplane {
    // ...
    getCruisingAltitude() {
        throw new Error('Must be implemented by subclass');
    }
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

**Why is this better?**

-   Each airplane type handles its own altitude calculation

-   Adding new airplane types doesn't require modifying existing code

-   Class responsibilities are clearly defined

-   Easier to test each airplane type independently

-   Follows the Open/Closed Principle

-   No need for switch statements or conditionals

-   Each class can have its own specialized methods

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
