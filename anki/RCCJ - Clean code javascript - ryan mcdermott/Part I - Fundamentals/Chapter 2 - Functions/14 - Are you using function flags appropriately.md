========== Question ==========  

### Are you using function flags appropriately?

Look at this code. What design issue do you see?

```javascript
function createFile(name, temp) {
    if (temp) {
        fs.create(`./temp/${name}`);
    } else {
        fs.create(name);
    }
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   What does the boolean parameter tell you about the function's responsibilities?

-   Is this function doing more than one thing?

-   How could we make the function's purpose clearer?

</details>  

========== Answer ==========  

**The Principle**:

Boolean flags in function parameters often indicate that a function is doing too much. When a function's behavior changes based on a boolean parameter, it's violating the Single Responsibility Principle.

**Solution**:

Here's a clearer way to write it:

```javascript
function createFile(name) {
    fs.create(name);
}

function createTempFile(name) {
    createFile(`./temp/${name}`);
}
```

**Why is this better?**

-   Each function has a single, clear purpose

-   Function names clearly describe what they do

-   No need to remember what the boolean parameter means

-   Easier to test and maintain

========== Id ==========  
14

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#14-Are-you-using-function-flags-appropriately

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
