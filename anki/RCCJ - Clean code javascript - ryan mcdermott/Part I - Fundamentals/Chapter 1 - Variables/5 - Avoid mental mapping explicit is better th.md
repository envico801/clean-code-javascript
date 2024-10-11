========== Question ==========  

### Avoid Mental Mapping

Explicit is better than implicit.

**Bad:**

```javascript
const locations = ['Austin', 'New York', 'San Francisco'];
locations.forEach((l) => {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `l` for again?
    dispatch(l);
});
```  

========== Answer ==========  

**Good:**

```javascript
const locations = ['Austin', 'New York', 'San Francisco'];
locations.forEach((location) => {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    dispatch(location);
});
```

========== Id ==========  
5

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#5-Avoid-mental-mapping-explicit-is-better-th

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
