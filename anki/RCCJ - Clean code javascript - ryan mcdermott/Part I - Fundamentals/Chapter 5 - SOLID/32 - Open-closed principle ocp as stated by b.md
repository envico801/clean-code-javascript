========== Question ==========  

### Open/Closed Principle (OCP)

As stated by Bertrand Meyer, "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification." What does that mean though? This principle basically states that you should allow users to add new functionalities without changing existing code.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-5-SOLID::#32-Open-closed-principle-ocp-as-stated-by-b

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
