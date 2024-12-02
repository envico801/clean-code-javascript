========== Question ==========  

### Are you adhering to the Interface Segregation Principle (ISP)?

Look at this code. What's problematic about how the DOMTraverser class is designed?

```javascript
class DOMTraverser {
    constructor(settings) {
        this.settings = settings;
        this.setup();
    }

    setup() {
        this.rootNode = this.settings.rootNode;
        this.settings.animationModule.setup();
    }

    traverse() {
        // ... traversal logic
    }
}

// Usage:
const $ = new DOMTraverser({
    rootNode: document.getElementsByTagName('body'),
    animationModule() {}, // Forced to provide animation module even if not needed
    // ...
});
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What if we don't need animations?

-   Are we forcing users to provide unnecessary functionality?

-   How could we make the animation module optional?

-   What if we want to add more optional features later?

</details>  

========== Answer ==========  

**The Principle**:

The Interface Segregation Principle states that clients should not be forced to depend on interfaces they don't use. In JavaScript, this means classes shouldn't be forced to implement methods or provide dependencies they don't need.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#interface-segregation-principle-isp](https://github.com/ryanmcdermott/clean-code-javascript#interface-segregation-principle-isp)

**Solution**:

Here's a better approach:

```javascript
class DOMTraverser {
    constructor(settings) {
        this.settings = settings;
        this.options = settings.options;
        this.setup();
    }

    setup() {
        this.rootNode = this.settings.rootNode;
        this.setupOptions();
    }

    setupOptions() {
        if (this.options.animationModule) {
            // ...
        }
    }

    traverse() {
        // ...
    }
}

const $ = new DOMTraverser({
    rootNode: document.getElementsByTagName('body'),
    options: {
        animationModule() {},
    },
});
```

**Why is this better?**

1. Animation module is now optional

2. Users only need to provide what they actually use

3. The code is more flexible and extensible

4. New optional features can be easily added without breaking existing code

========== Id ==========  
34

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 5 - SOLID

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#34-Are-you-adhering-to-the-interface-segregat

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
