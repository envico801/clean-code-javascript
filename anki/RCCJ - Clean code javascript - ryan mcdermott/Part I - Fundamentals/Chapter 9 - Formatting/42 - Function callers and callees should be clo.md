========== Question ==========  

### Function callers and callees should be close

If a function calls another, keep those functions vertically close in the source file. Ideally, keep the caller right above the callee. We tend to read code from top-to-bottom, like a newspaper. Because of this, make your code read that way.

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

**Good:**

```javascript
class PerformanceReview {
    constructor(employee) {
        this.employee = employee;
    }
    perfReview() {
        this.getPeerReviews();
        this.getManagerReview();
        this.getSelfReview();
    }
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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-9-Formatting::#42-Function-callers-and-callees-should-be-clo

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
