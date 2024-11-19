========== Question ==========  

### Are you avoiding writing to global functions?

Extending built-in objects through their prototypes (like Array, String, etc.) can lead to naming conflicts and unexpected behavior in your application, especially when multiple libraries are involved.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#dont-write-to-global-functions](https://github.com/ryanmcdermott/clean-code-javascript#dont-write-to-global-functions)

**Bad:**

```javascript
Array.prototype.diff = function diff(comparisonArray) {
    const hash = new Set(comparisonArray);
    return this.filter((elem) => !hash.has(elem));
};
```  

========== Answer ==========  

Use classes and inheritance to extend functionality instead of modifying global prototypes. This provides a cleaner, more maintainable way to add custom functionality.

**Good:**

```javascript
class SuperArray extends Array {
    diff(comparisonArray) {
        const hash = new Set(comparisonArray);
        return this.filter((elem) => !hash.has(elem));
    }
}
```

========== Id ==========  
17

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#17-Are-you-avoiding-writing-to-global-functio

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
