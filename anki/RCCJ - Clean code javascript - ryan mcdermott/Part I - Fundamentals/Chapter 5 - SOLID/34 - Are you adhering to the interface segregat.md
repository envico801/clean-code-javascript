========== Question ==========  

### Are you adhering to the Interface Segregation Principle (ISP)?

The Interface Segregation Principle states that clients should not be forced to depend on interfaces they don't use. In JavaScript, where interfaces are implicit, this means classes shouldn't be forced to implement methods they don't need.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#interface-segregation-principle-isp](https://github.com/ryanmcdermott/clean-code-javascript#interface-segregation-principle-isp)

**Bad:**

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
        // ...
    }
}

const $ = new DOMTraverser({
    rootNode: document.getElementsByTagName('body'),
    animationModule() {}, // Forced to provide animation module even if not needed
    // ...
});
```  

========== Answer ==========  

The improved version makes the animation module optional through a separate options object, following ISP by not forcing clients to implement unnecessary functionality.

**Good:**

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
