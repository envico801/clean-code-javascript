========== Question ==========  

### Are you preventing unintended side effects in shared data structures? (Part 2)

Mutable data structures can lead to unintended side effects when shared across different parts of your application. When modifying objects or arrays that are passed as parameters, you risk affecting code elsewhere that uses those same references.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-2](https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-2)

**Bad:**

```javascript
const addItemToCart = (cart, item) => {
    cart.push({ item, date: Date.now() });
};
```  

========== Answer ==========  

Instead of modifying input parameters, create and return new objects/arrays. This immutable approach helps prevent bugs and makes code behavior more predictable.

**Good:**

```javascript
const addItemToCart = (cart, item) => {
    return [...cart, { item, date: Date.now() }];
};
```

========== Id ==========  
16

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#16-Are-you-preventing-unintended-side-effects

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
