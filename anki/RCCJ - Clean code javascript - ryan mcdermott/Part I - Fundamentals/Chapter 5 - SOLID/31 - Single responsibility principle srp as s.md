========== Question ==========  

### Single Responsibility Principle (SRP)

As stated in Clean Code, "There should never be more than one reason for a class

to change". It's tempting to jam-pack a class with a lot of functionality, like

when you can only take one suitcase on your flight. The issue with this is

that your class won't be conceptually cohesive and it will give it many reasons

to change. Minimizing the amount of times you need to change a class is important.

It's important because if too much functionality is in one class and you modify

a piece of it, it can be difficult to understand how that will affect other

dependent modules in your codebase.

**Bad:**

```javascript
class UserSettings {
    constructor(user) {
        this.user = user;
    }
    changeSettings(settings) {
        if (this.verifyCredentials()) {
            // ...
        }
    }
    verifyCredentials() {
        // ...
    }
}
```  

========== Answer ==========  

**Good:**

```javascript
class UserAuth {
    constructor(user) {
        this.user = user;
    }
    verifyCredentials() {
        // ...
    }
}
class UserSettings {
    constructor(user) {
        this.user = user;
        this.auth = new UserAuth(user);
    }
    changeSettings(settings) {
        if (this.auth.verifyCredentials()) {
            // ...
        }
    }
}
```

========== Id ==========  
31

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 5 - SOLID

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#31-Single-responsibility-principle-srp-as-s

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
