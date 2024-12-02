========== Question ==========  

### Does each function do only one thing?

What's wrong with this function's responsibilities?

```javascript
function emailClients(clients) {
    clients.forEach((client) => {
        const clientRecord = database.lookup(client);
        if (clientRecord.isActive()) {
            email(client);
        }
    });
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   How many different operations is this function performing?

-   What if you needed to reuse just the active client check?

-   How could we make this more modular?

</details>  

========== Answer ==========  

**The Principle**:

Functions should have a single responsibility - they should do one thing, and do it well.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing](https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing)

**Solution**:

```javascript
function emailActiveClients(clients) {
    clients.filter(isActiveClient).forEach(email);
}

function isActiveClient(client) {
    const clientRecord = database.lookup(client);
    return clientRecord.isActive();
}
```

**Why is this better?**

We've separated the concerns into two functions: one checks if a client is active, and another handles sending emails. This makes the code more reusable and easier to test.

========== Id ==========  
9

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#9-Does-each-function-do-only-one-thing-what

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
