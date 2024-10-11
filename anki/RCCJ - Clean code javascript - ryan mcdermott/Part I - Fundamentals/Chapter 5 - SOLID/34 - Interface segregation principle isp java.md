========== Question ==========  

### Interface Segregation Principle (ISP)

JavaScript doesn't have interfaces so this principle doesn't apply as strictly

as others. However, it's important and relevant even with JavaScript's lack of

type system.

ISP states that "Clients should not be forced to depend upon interfaces that

they do not use." Interfaces are implicit contracts in JavaScript because of

duck typing.

A good example to look at that demonstrates this principle in JavaScript is for

classes that require large settings objects. Not requiring clients to setup

huge amounts of options is beneficial, because most of the time they won't need

all of the settings. Making them optional helps prevent having a

"fat interface".

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
    animationModule() {}, // Most of the time, we won't need to animate when traversing.
    // ...
});
```  

========== Answer ==========  

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#34-Interface-segregation-principle-isp-java

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
