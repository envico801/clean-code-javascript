========== Question ==========  

### Does your function name clearly describe its purpose?

Function names should be verbs that clearly describe the action being performed. Avoid vague or ambiguous names that don't convey the function's purpose.

**Bad:**

```javascript
function addToDate(date, month) {
    // ...
}

const date = new Date();

// It's hard to tell from the function name what is added
addToDate(date, 1);
```  

========== Answer ==========  

Use specific, action-oriented function names that clearly describe what the function does. The name should make it obvious what parameters are expected and what the function will do with them.

**Good:**

```javascript
function addMonthToDate(month, date) {
    // ...
}

const date = new Date();
addMonthToDate(1, date);
```

========== Id ==========  
10

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#10-Does-your-function-name-clearly-describe-i

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
