========== Question ==========  

### Are you following the Single Responsibility Principle (SRP)?

The Single Responsibility Principle states that a class should have only one reason to change. This means each class should focus on doing one specific thing well, rather than trying to handle multiple responsibilities. This makes code more maintainable, testable, and easier to understand.

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

By separating authentication from settings management, we create two classes that each have a single responsibility. This makes the code more modular and easier to modify without affecting other functionality.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#31-Are-you-following-the-single-responsibilit

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
