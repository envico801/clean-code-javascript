========== Question ==========  

### Do your functions have two or fewer arguments?

What makes this function call difficult to work with?

```javascript
function createMenu(title, body, buttonText, cancellable) {
    // ...
}

createMenu('Foo', 'Bar', 'Baz', true);
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   How easy is it to remember the order of parameters?

-   What happens if you want to add more options?

-   How would you skip optional parameters?

</details>  

========== Answer ==========  

**The Principle**:

Having too many function parameters makes your code harder to test and maintain. Each additional parameter exponentially increases the number of test cases needed.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#function-arguments-2-or-fewer-ideally](https://github.com/ryanmcdermott/clean-code-javascript#function-arguments-2-or-fewer-ideally)

**Solution**:

```javascript
function createMenu({ title, body, buttonText, cancellable }) {
    // ...
}

createMenu({
    title: 'Foo',
    body: 'Bar',
    buttonText: 'Baz',
    cancellable: true,
});
```

**Why is this better?**

Using an object with named parameters makes the function call self-documenting, allows optional parameters, and doesn't require remembering parameter order.

========== Id ==========  
8

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#8-Do-your-functions-have-two-or-fewer-argume

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
