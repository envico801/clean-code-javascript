========== Question ==========  

### Does your function name clearly describe its purpose?

What's unclear about this function name and usage?

```javascript
function addToDate(date, month) {
    // ...
}

const date = new Date();

// It's hard to tell from the function name what is added
addToDate(date, 1);
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What exactly is being added to the date?

-   Is the parameter order intuitive?

-   How could you make the function's purpose more obvious?

</details>  

========== Answer ==========  

**The Principle**:

Function names should be verbs that clearly describe the action being performed. Avoid vague or ambiguous names that don't convey the function's purpose.

**Solution**:

```javascript
function addMonthToDate(month, date) {
    // ...
}

const date = new Date();
addMonthToDate(1, date);
```

**Why is this better?**

The function name now explicitly states what it's adding (a month), and the parameter order follows the natural language order of the function name.

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
