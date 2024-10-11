========== Question ==========  

### Avoid negative conditionals

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#20-Avoid-negative-conditionals-bad-ja

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
