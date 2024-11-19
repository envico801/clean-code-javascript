========== Question ==========  

### Are you avoiding flags as function parameters?

Boolean flags in function parameters often indicate that a function is doing too much. When a function's behavior changes based on a boolean parameter, it's violating the Single Responsibility Principle.

**Bad:**

```javascript
function createFile(name, temp) {
    if (temp) {
        fs.create(`./temp/${name}`);
    } else {
        fs.create(name);
    }
}
```  

========== Answer ==========  

Split the function into two separate functions, each with a clear, single purpose. This makes the code's intent clearer and follows the Single Responsibility Principle.

**Good:**

```javascript
function createFile(name) {
    fs.create(name);
}

function createTempFile(name) {
    createFile(`./temp/${name}`);
}
```

========== Id ==========  
14

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#14-Are-you-avoiding-flags-as-function-paramet

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
