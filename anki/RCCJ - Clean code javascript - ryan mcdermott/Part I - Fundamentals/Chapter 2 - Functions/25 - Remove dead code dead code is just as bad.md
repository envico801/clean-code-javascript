========== Question ==========  

### Remove dead code

Dead code is just as bad as duplicate code. There's no reason to keep it in your codebase. If it's not being called, get rid of it! It will still be safe in your version history if you still need it.

**Bad:**

```javascript
function oldRequestModule(url) {
    // ...
}
function newRequestModule(url) {
    // ...
}
const req = newRequestModule;
inventoryTracker('apples', req, 'www.inventory-awesome.io');
```  

========== Answer ==========  

**Good:**

```javascript
function newRequestModule(url) {
    // ...
}
const req = newRequestModule;
inventoryTracker('apples', req, 'www.inventory-awesome.io');
```

========== Id ==========  
25

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#25-Remove-dead-code-dead-code-is-just-as-bad

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
