========== Question ==========  

### Are you using default parameters instead of short-circuiting or conditionals?

Default parameters provide a cleaner way to handle missing values in function parameters. They make the intended default value explicit in the function signature.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#use-default-parameters-instead-of-short-circuiting-or-conditionals](https://github.com/ryanmcdermott/clean-code-javascript#use-default-parameters-instead-of-short-circuiting-or-conditionals)

**Bad:**

```javascript
function createMicrobrewery(name) {
    const breweryName = name || 'Hipster Brew Co.';
    // ...
}
```  

========== Answer ==========  

ES6 default parameters make the code more intentional and clearer. They only trigger when the parameter is `undefined`, providing more predictable behavior than logical OR operations.

**Good:**

```javascript
function createMicrobrewery(name = 'Hipster Brew Co.') {
    // ...
}
```

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
