========== Question ==========  

### Does each function do only one thing?

A fundamental principle of clean code is that functions should have a single responsibility. This makes them easier to understand, test, and maintain.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing](https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing)

**Bad:**

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

========== Answer ==========  

Break down complex functions into smaller, focused functions that each do one thing. This improves code reusability and makes the code's intent clearer.

**Good:**

```javascript
function emailActiveClients(clients) {
    clients.filter(isActiveClient).forEach(email);
}

function isActiveClient(client) {
    const clientRecord = database.lookup(client);
    return clientRecord.isActive();
}
```

========== Id ==========  
9

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#9-Does-each-function-do-only-one-thing-a-fu

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
