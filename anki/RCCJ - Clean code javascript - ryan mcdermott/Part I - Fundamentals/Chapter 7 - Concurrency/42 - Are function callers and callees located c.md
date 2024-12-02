========== Question ==========  

### Are function callers and callees located close to each other?

Look at this code. Can you spot the problems with its organization?

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

<details><summary>🔍 Hints</summary>

Think about:

-   How are related functions positioned relative to each other?

-   Which functions call other functions?

-   How many times do you need to scroll up and down to understand the flow?

-   What would make the code easier to read?

</details>  

========== Answer ==========  

**The Principle:**

Code organization impacts readability and maintainability. Functions that work together should be located close to each other in the source file. This principle follows natural reading patterns and makes it easier to understand the flow of the program.

**Solution**:

Here's how to better organize the code:

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

**Why is this better?**

-   The main workflow function (`perfReview`) is at the top

-   Helper functions are grouped with the functions that call them

-   Related functions are kept together (e.g., `getManagerReview` next to `lookupManager`)

-   The code flows more naturally, reducing the need to jump around while reading

========== Id ==========  
42

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 7 - Concurrency

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#42-Are-function-callers-and-callees-located-c

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
