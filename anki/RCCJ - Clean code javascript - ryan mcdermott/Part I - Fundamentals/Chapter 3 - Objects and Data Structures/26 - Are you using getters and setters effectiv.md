========== Question ==========  

### Are you using getters and setters effectively?

Getters and setters provide a way to control access to object properties, enabling better encapsulation and more flexible property management. They allow you to add validation, logging, or other behaviors without changing the interface.

Key benefits of getters and setters:

-   Enhanced encapsulation

-   Ability to add validation logic

-   Easy to implement computed properties

-   Facilitates logging and debugging

-   Enables lazy loading of properties

**Bad:**

```javascript
function makeBankAccount() {
    // ...

    return {
        balance: 0,
        // ...
    };
}

const account = makeBankAccount();
account.balance = 100;
```  

========== Answer ==========  

Using getters and setters provides better control over property access and modification, allowing for validation, logging, and other behaviors to be added without changing the interface.

**Good:**

```javascript
function makeBankAccount() {
    let balance = 0; // private variable

    // a "getter", made public via the returned object below
    function getBalance() {
        // Add logging if needed
        console.log('Balance accessed');
        return balance;
    }

    // a "setter", made public via the returned object below
    function setBalance(amount) {
        // Validate before updating
        if (amount < 0) {
            throw new Error('Balance cannot be negative');
        }
        balance = amount;
    }

    return {
        // ...
        getBalance,
        setBalance,
    };
}

const account = makeBankAccount();
account.setBalance(100);
```

========== Id ==========  
26

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 3 - Objects and Data Structures

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-3-Objects-and-Data-Structures::#26-Are-you-using-getters-and-setters-effectiv

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
