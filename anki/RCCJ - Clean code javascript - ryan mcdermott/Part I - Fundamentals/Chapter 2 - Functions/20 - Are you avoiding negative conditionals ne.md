========== Question ==========  

### Are you avoiding negative conditionals?

Negative conditionals are harder to understand at a glance because they require additional mental processing to understand what the code is not doing rather than what it is doing.

**Bad:**

```javascript
function isDOMNodeNotPresent(node) {
    // ...
}

if (!isDOMNodeNotPresent(node)) {
    // ...
}
```  

========== Answer ==========  

Use positive conditionals to make code more intuitive and easier to read. This reduces cognitive load and makes the code's intent clearer.

**Good:**

```javascript
function isDOMNodePresent(node) {
    // ...
}

if (isDOMNodePresent(node)) {
    // ...
}
```

========== Id ==========  
20

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#20-Are-you-avoiding-negative-conditionals-ne

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
