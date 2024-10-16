========== Question ==========  

### Use getters and setters

Using getters and setters to access data on objects could be better than simply

looking for a property on an object. "Why?" you might ask. Well, here's an

unorganized list of reasons why:

-   When you want to do more beyond getting an object property, you don't have

    to look up and change every accessor in your codebase.

-   Makes adding validation simple when doing a `set`.

-   Encapsulates the internal representation.

-   Easy to add logging and error handling when getting and setting.

-   You can lazy load your object's properties, let's say getting it from a

    server.

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

**Good:**

```javascript
function makeBankAccount() {
    // this one is private
    let balance = 0;
    // a "getter", made public via the returned object below
    function getBalance() {
        return balance;
    }
    // a "setter", made public via the returned object below
    function setBalance(amount) {
        // ... validate before updating the balance
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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-3-Objects-and-Data-Structures::#26-Use-getters-and-setters-using-getters-and

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
