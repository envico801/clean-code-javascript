========== Question ==========  

### Are you avoiding side effects in your functions? (Part 2)

What potential problems could this cart implementation cause?

```javascript
const addItemToCart = (cart, item) => {
    cart.push({ item, date: Date.now() });
};
```

<details><summary>🔍 Hints</summary>

Think about:

-   What happens to the original cart array?

-   Could this cause issues if multiple parts of the code use the same cart?

-   How would you track changes to the cart?

-   What's a more predictable way to handle this?

</details>  

========== Answer ==========  

**The Principle**:

Mutable data structures can lead to unintended side effects when shared across different parts of your application. When modifying objects or arrays that are passed as parameters, you risk affecting code elsewhere that uses those same references. Instead, create new copies with your changes to prevent unintended side effects.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-2](https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-2)

**Solution**:

Here's a safer approach:

```javascript
const addItemToCart = (cart, item) => {
    return [...cart, { item, date: Date.now() }];
};
```

**Why is this better?**

-   Returns a new cart array instead of modifying the existing one

-   Original cart remains unchanged for other code to use

-   Easier to track changes (good for state management)

-   Prevents bugs from unexpected mutations

-   Makes it easier to implement features like undo/redo

========== Id ==========  
16

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#16-Are-you-avoiding-side-effects-in-your-func

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
