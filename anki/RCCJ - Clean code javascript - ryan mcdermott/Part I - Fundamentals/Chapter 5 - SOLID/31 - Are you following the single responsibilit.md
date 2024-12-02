========== Question ==========  

### Are you following the Single Responsibility Principle (SRP)?

Look at this code. What's wrong with it?

```javascript
class UserSettings {
    constructor(user) {
        this.user = user;
    }

    changeSettings(settings) {
        if (this.verifyCredentials()) {
            // ... change settings
        }
    }

    verifyCredentials() {
        // ... check user credentials
    }
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   How many different responsibilities does this class have?

-   What if authentication rules change?

-   What if settings logic changes?

-   Could these responsibilities be separated?

-   What's the "single reason to change" for this class?

</details>  

========== Answer ==========  

**The Principle**:

The Single Responsibility Principle states that a class should have only one reason to change. This means each class should focus on doing one specific thing well, rather than trying to handle multiple responsibilities. This makes code more maintainable, testable, and easier to understand.

**Solution**:

```javascript
class UserAuth {
    constructor(user) {
        this.user = user;
    }

    verifyCredentials() {
        // ... check user credentials
    }
}

class UserSettings {
    constructor(user) {
        this.user = user;
        this.auth = new UserAuth(user);
    }

    changeSettings(settings) {
        if (this.auth.verifyCredentials()) {
            // ... change settings
        }
    }
}
```

**Why is this better?**

-   Each class has a single responsibility

-   Authentication logic is separate from settings management

-   Changes to auth don't affect settings and vice versa

-   Easier to test each component independently

-   More maintainable and flexible design

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
