========== Question ==========  

### Are you avoiding writing to global functions?

What's problematic about this code's approach to extending Array functionality?

```javascript
Array.prototype.diff = function diff(comparisonArray) {
    const hash = new Set(comparisonArray);
    return this.filter((elem) => !hash.has(elem));
};
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens if different libraries try to add a `diff` method?

-   Could this break existing code that uses arrays?

-   How could we add this functionality without modifying the Array prototype?

-   What's a more maintainable way to extend functionality?

</details>  

========== Answer ==========  

**The Principle**:

Extending built-in objects through their prototypes (like Array, String, etc.) can lead to naming conflicts and unexpected behavior in your application, especially when multiple libraries are involved.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#dont-write-to-global-functions](https://github.com/ryanmcdermott/clean-code-javascript#dont-write-to-global-functions)

**Solution**:

Here's a safer way to implement this functionality:

```javascript
class SuperArray extends Array {
    diff(comparisonArray) {
        const hash = new Set(comparisonArray);
        return this.filter((elem) => !hash.has(elem));
    }
}
```

**Why is this better?**

-   Doesn't modify global Array prototype

-   Functionality is isolated to specific use cases

-   No risk of naming conflicts with other libraries

-   Clear where the enhanced functionality comes from

-   Easier to maintain and test

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
