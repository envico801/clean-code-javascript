========== Question ==========  

### Avoid conditionals

This seems like an impossible task. Upon first hearing this, most people say,

"how am I supposed to do anything without an `if` statement?" The answer is that

you can use polymorphism to achieve the same task in many cases. The second

question is usually, "well that's great but why would I want to do that?" The

answer is a previous clean code concept we learned: a function should only do

one thing. When you have classes and functions that have `if` statements, you

are telling your user that your function does more than one thing. Remember,

just do one thing.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#21-Avoid-conditionals-this-seems-like-an-impo

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
