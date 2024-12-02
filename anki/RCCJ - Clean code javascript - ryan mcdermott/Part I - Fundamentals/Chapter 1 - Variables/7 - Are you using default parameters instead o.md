========== Question ==========  

### Are you using default parameters instead of short-circuiting or conditionals?

Look at this code. What could be improved?

```javascript
function createMicrobrewery(name) {
    const breweryName = name || 'Hipster Brew Co.';
    // ...
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens if name is an empty string?

-   What happens if name is 0?

-   Is there a clearer way to express the default value?

</details>  

========== Answer ==========  

**The Principle**:

Use ES6 default parameters to handle missing values instead of logical operators that might have unexpected behavior with falsy values.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#use-default-parameters-instead-of-short-circuiting-or-conditionals](https://github.com/ryanmcdermott/clean-code-javascript#use-default-parameters-instead-of-short-circuiting-or-conditionals)

**Solution**:

```javascript
function createMicrobrewery(name = 'Hipster Brew Co.') {
    // ...
}
```

**Why is this better?**

Default parameters only trigger when the value is `undefined`, providing more predictable behavior than the logical OR operator which can override any falsy value.

========== Id ==========  
7

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#7-Are-you-using-default-parameters-instead-o

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
