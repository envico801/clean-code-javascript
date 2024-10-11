========== Question ==========  

### Don't ignore rejected promises

For the same reason you shouldn't ignore caught errors

from `try/catch`.

**Bad:**

```javascript
getdata()
    .then((data) => {
        functionThatMightThrow(data);
    })
    .catch((error) => {
        console.log(error);
    });
```  

========== Answer ==========  

**Good:**

```javascript
getdata()
    .then((data) => {
        functionThatMightThrow(data);
    })
    .catch((error) => {
        // One option (more noisy than console.log):
        console.error(error);
        // Another option:
        notifyUserOfError(error);
        // Another option:
        reportErrorToService(error);
        // OR do all three!
    });
```

========== Id ==========  
40

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 8 - Error Handling

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-8-Error-Handling::#40-Don-t-ignore-rejected-promises-for-the-sam

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
