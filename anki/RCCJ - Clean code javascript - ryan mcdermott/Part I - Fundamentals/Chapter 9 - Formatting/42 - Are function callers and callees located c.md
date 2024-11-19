========== Question ==========  

### Are function callers and callees located close to each other?

Code organization impacts readability and maintainability. Functions that work together should be located close to each other in the source file. This principle follows natural reading patterns and makes it easier to understand the flow of the program.

**Bad:**

```javascript
class PerformanceReview {
    constructor(employee) {
        this.employee = employee;
    }

    lookupPeers() {
        return db.lookup(this.employee, 'peers');
    }

    lookupManager() {
        return db.lookup(this.employee, 'manager');
    }

    getPeerReviews() {
        const peers = this.lookupPeers();
        // ...
    }

    perfReview() {
        this.getPeerReviews();
        this.getManagerReview();
        this.getSelfReview();
    }

    getManagerReview() {
        const manager = this.lookupManager();
    }

    getSelfReview() {
        // ...
    }
}

const review = new PerformanceReview(employee);
review.perfReview();
```  

========== Answer ==========  

Organizing related functions close together improves code readability by:

-   Making the code flow more natural to follow

-   Reducing the need to jump around the file

-   Making relationships between functions more obvious

-   Facilitating easier code maintenance and updates

**Good:**

```javascript
class PerformanceReview {
    constructor(employee) {
        this.employee = employee;
    }

    // Main workflow function at the top
    perfReview() {
        this.getPeerReviews();
        this.getManagerReview();
        this.getSelfReview();
    }

    // Grouped related functions together
    getPeerReviews() {
        const peers = this.lookupPeers();
        // ...
    }

    lookupPeers() {
        return db.lookup(this.employee, 'peers');
    }

    getManagerReview() {
        const manager = this.lookupManager();
    }

    lookupManager() {
        return db.lookup(this.employee, 'manager');
    }

    getSelfReview() {
        // ...
    }
}

const review = new PerformanceReview(employee);
review.perfReview();
```

========== Id ==========  
42

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 9 - Formatting

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-9-Formatting::#42-Are-function-callers-and-callees-located-c

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
