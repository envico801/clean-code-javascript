========== Question ==========  

### Use default parameters instead of short circuiting or conditionals

Default parameters are often cleaner than short circuiting. Be aware that if you

use them, your function will only provide default values for `undefined`

arguments. Other "falsy" values such as `''`, `""`, `false`, `null`, `0`, and

`NaN`, will not be replaced by a default value.

**Bad:**

```javascript
function createMicrobrewery(name) {
    const breweryName = name || 'Hipster Brew Co.';
    // ...
}
```  

========== Answer ==========  

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#7-Use-default-parameters-instead-of-short-ci

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
