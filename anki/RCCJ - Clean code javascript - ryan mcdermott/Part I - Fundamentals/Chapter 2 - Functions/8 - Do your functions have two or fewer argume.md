========== Question ==========  

### Do your functions have two or fewer arguments?

Having too many function parameters makes your code harder to test and maintain. Each additional parameter exponentially increases the number of test cases needed.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#function-arguments-2-or-fewer-ideally](https://github.com/ryanmcdermott/clean-code-javascript#function-arguments-2-or-fewer-ideally)

**Bad:**

```javascript
function createMenu(title, body, buttonText, cancellable) {
    // ...
}

createMenu('Foo', 'Bar', 'Baz', true);
```  

========== Answer ==========  

Use object destructuring when you need multiple parameters. This makes the function call more readable and allows for optional parameters without maintaining a specific order.

**Good:**

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
