========== Question ==========  

### Are you adhering to the Open/Closed Principle (OCP)?

The Open/Closed Principle states that software entities should be open for extension but closed for modification. This means you should be able to add new functionality without changing existing code, typically achieved through inheritance and polymorphism.

**Bad:**

```javascript
class AjaxAdapter extends Adapter {
    constructor() {
        super();
        this.name = 'ajaxAdapter';
    }
}

class NodeAdapter extends Adapter {
    constructor() {
        super();
        this.name = 'nodeAdapter';
    }
}

class HttpRequester {
    constructor(adapter) {
        this.adapter = adapter;
    }

    fetch(url) {
        if (this.adapter.name === 'ajaxAdapter') {
            return makeAjaxCall(url).then((response) => {
                // transform response and return
            });
        } else if (this.adapter.name === 'nodeAdapter') {
            return makeHttpCall(url).then((response) => {
                // transform response and return
            });
        }
    }
}

function makeAjaxCall(url) {
    // request and return promise
}

function makeHttpCall(url) {
    // request and return promise
}
```  

========== Answer ==========  

The improved version demonstrates OCP by allowing new adapters to be added without modifying the HttpRequester class. Each adapter implements a common interface (the request method), making the system extensible.

**Good:**

```javascript
class AjaxAdapter extends Adapter {
    constructor() {
        super();
        this.name = 'ajaxAdapter';
    }

    request(url) {
        // request and return promise
    }
}

class NodeAdapter extends Adapter {
    constructor() {
        super();
        this.name = 'nodeAdapter';
    }

    request(url) {
        // request and return promise
    }
}

class HttpRequester {
    constructor(adapter) {
        this.adapter = adapter;
    }

    fetch(url) {
        return this.adapter.request(url).then((response) => {
            // transform response and return
        });
    }
}
```

========== Id ==========  
32

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 5 - SOLID

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#32-Are-you-adhering-to-the-open-closed-princi

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
