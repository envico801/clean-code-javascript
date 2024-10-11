========== Question ==========  

### Don't over-optimize

Modern browsers do a lot of optimization under-the-hood at runtime. A lot of

times, if you are optimizing then you are just wasting your time. [There are good

resources](https://github.com/petkaantonov/bluebird/wiki/Optimization-killers)

for seeing where optimization is lacking. Target those in the meantime, until

they are fixed if they can be.

**Bad:**

```javascript
// On old browsers, each iteration with uncached `list.length` would be costly
// because of `list.length` recomputation. In modern browsers, this is optimized.
for (let i = 0, len = list.length; i < len; i++) {
    // ...
}
```  

========== Answer ==========  

**Good:**

```javascript
for (let i = 0; i < list.length; i++) {
    // ...
}
```

========== Id ==========  
24

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#24-Don-t-over-optimize-modern-browsers-do-a-l

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
