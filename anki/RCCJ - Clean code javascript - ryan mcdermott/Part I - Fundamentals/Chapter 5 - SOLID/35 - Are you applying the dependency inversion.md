========== Question ==========  

### Are you applying the Dependency Inversion Principle (DIP)?

The Dependency Inversion Principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions. This promotes loose coupling and makes the code more flexible and easier to modify.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#dependency-inversion-principle-dip](https://github.com/ryanmcdermott/clean-code-javascript#dependency-inversion-principle-dip)

**Bad:**

```javascript
class InventoryRequester {
    constructor() {
        this.REQ_METHODS = ['HTTP'];
    }

    requestItem(item) {
        // ...
    }
}

class InventoryTracker {
    constructor(items) {
        this.items = items;
        // Bad: Directly creating an instance of a specific requester
        this.requester = new InventoryRequester();
    }

    requestItems() {
        this.items.forEach((item) => {
            this.requester.requestItem(item);
        });
    }
}

const inventoryTracker = new InventoryTracker(['apples', 'bananas']);
inventoryTracker.requestItems();
```  

========== Answer ==========  

The improved version implements DIP by:

1. Injecting the requester dependency

2. Allowing different types of requesters to be used

3. Making the high-level module (InventoryTracker) independent of specific implementations

**Good:**

```javascript
class InventoryTracker {
    constructor(items, requester) {
        this.items = items;
        this.requester = requester;
    }

    requestItems() {
        this.items.forEach((item) => {
            this.requester.requestItem(item);
        });
    }
}

class InventoryRequesterV1 {
    constructor() {
        this.REQ_METHODS = ['HTTP'];
    }

    requestItem(item) {
        // ...
    }
}

class InventoryRequesterV2 {
    constructor() {
        this.REQ_METHODS = ['WS'];
    }

    requestItem(item) {
        // ...
    }
}

// By constructing our dependencies externally and injecting them, we can easily
// substitute our request module for a fancy new one that uses WebSockets.
const inventoryTracker = new InventoryTracker(
    ['apples', 'bananas'],
    new InventoryRequesterV2(),
);
inventoryTracker.requestItems();
```

========== Id ==========  
35

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 5 - SOLID

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#35-Are-you-applying-the-dependency-inversion

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
