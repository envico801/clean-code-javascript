========== Question ==========  

### Are you setting default objects with `Object.assign`?

What's problematic about this code?

```javascript
const menuConfig = {
    title: null,
    body: 'Bar',
    buttonText: null,
    cancellable: true,
};

function createMenu(config) {
    config.title = config.title || 'Foo';
    config.body = config.body || 'Bar';
    config.buttonText = config.buttonText || 'Baz';
    config.cancellable =
        config.cancellable !== undefined ? config.cancellable : true;
}

createMenu(menuConfig);
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens to the original config object?

-   Is this code immutable?

-   How could we make this cleaner using modern JavaScript?

</details>  

========== Answer ==========  

**The Principle**:

When working with objects that need default values, using `Object.assign` or the spread operator provides a cleaner and more maintainable way to set default properties compared to manual property assignments.

**Solution**:

Here's a better approach:

```javascript
const menuConfig = {
    title: 'Order',
    // User did not include 'body' key
    buttonText: 'Send',
    cancellable: true,
};

function createMenu(config) {
    let finalConfig = Object.assign(
        {
            title: 'Foo',
            body: 'Bar',
            buttonText: 'Baz',
            cancellable: true,
        },
        config,
    );
    return finalConfig;
    // config now equals: {title: "Order", body: "Bar", buttonText: "Send", cancellable: true}
    // ...
}

createMenu(menuConfig);
```

**Why is this better?**

-   Original config object remains unchanged

-   All defaults are clearly defined in one place

-   More declarative and easier to understand

-   Returns a new object instead of modifying the input

========== Id ==========  
13

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#13-Are-you-setting-default-objects-with-obje

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
