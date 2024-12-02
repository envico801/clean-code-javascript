========== Question ==========  

### Are you applying the Dependency Inversion Principle (DIP)?

Look at this code. What's problematic about how the InventoryTracker is implemented?

```javascript
class InventoryRequester {
    constructor() {
        this.REQ_METHODS = ['HTTP'];
    }

    requestItem(item) {
        // ... HTTP request implementation
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

// Usage:
const inventoryTracker = new InventoryTracker(['apples', 'bananas']);
inventoryTracker.requestItems();
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What if we want to use a different type of requester?

-   How tightly coupled is InventoryTracker to InventoryRequester?

-   What if we want to use WebSockets instead of HTTP?

-   How could we make this more flexible?

</details>  

========== Answer ==========  

**The Principle**:

The Dependency Inversion Principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions. This promotes loose coupling and makes the code more flexible and easier to modify.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#dependency-inversion-principle-dip](https://github.com/ryanmcdermott/clean-code-javascript#dependency-inversion-principle-dip)

**Solution**:

Here's a better approach:

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

class InventoryRequesterHTTP {
    constructor() {
        this.REQ_METHODS = ['HTTP'];
    }

    requestItem(item) {
        // ... HTTP request implementation
    }
}

class InventoryRequesterWS {
    constructor() {
        this.REQ_METHODS = ['WS'];
    }

    requestItem(item) {
        // ... WebSocket request implementation
    }
}

// Usage:
const httpTracker = new InventoryTracker(
    ['apples', 'bananas'],
    new InventoryRequesterHTTP(),
);

const wsTracker = new InventoryTracker(
    ['apples', 'bananas'],
    new InventoryRequesterWS(),
);

httpTracker.requestItems();
wsTracker.requestItems();
```

**Why is this better?**

1. InventoryTracker is no longer tightly coupled to a specific requester

2. We can easily swap different types of requesters

3. Testing becomes easier as we can mock the requester

4. New request methods can be added without modifying existing code

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
