========== Question ==========  

### Are you setting default objects with `Object.assign`?

When working with objects that need default values, using `Object.assign` or the spread operator provides a cleaner and more maintainable way to set default properties compared to manual property assignments.

**Bad:**

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

========== Answer ==========  

Use `Object.assign` to create a new object that combines default values with provided configuration. This approach is more declarative and prevents mutation of the original config object.

**Good:**

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
