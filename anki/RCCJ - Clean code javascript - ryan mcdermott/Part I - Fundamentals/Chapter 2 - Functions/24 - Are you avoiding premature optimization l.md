========== Question ==========  

### Are you avoiding premature optimization?

Look at this code. What's wrong with it?

```javascript
// On old browsers, each iteration with uncached `list.length` would be costly
// because of `list.length` recomputation. In modern browsers, this is optimized.
for (let i = 0, len = list.length; i < len; i++) {
    // ...
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   Is this optimization actually necessary in modern browsers?

-   What's more important: code readability or micro-optimizations?

-   How do modern JavaScript engines handle loop optimizations?

-   Are we making assumptions about performance without measuring?

</details>  

========== Answer ==========  

**The Principle**:

Premature optimization can lead to harder-to-maintain code without providing meaningful performance benefits. Modern JavaScript engines are highly sophisticated and handle many optimizations automatically. Focus on writing clear, maintainable code first.

Key principles:

-   Trust the JavaScript engine's built-in optimizations

-   Focus on writing clear, maintainable code first

-   Only optimize after profiling identifies actual bottlenecks

-   Consider browser compatibility when optimizing

**Reference**:

-   [https://github.com/petkaantonov/bluebird/wiki/Optimization-killers](https://github.com/petkaantonov/bluebird/wiki/Optimization-killers)

**Solution**:

```javascript
for (let i = 0; i < list.length; i++) {
    // ...
}
```

**Why is this better?**

-   More readable and straightforward

-   Modern browsers optimize this automatically

-   No premature optimization

-   Easier to maintain

========== Id ==========  
24

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#24-Are-you-avoiding-premature-optimization-l

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
