========== Question ==========  

### Set default objects with Object.assign

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#13-Set-default-objects-with-object-assign-b

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
