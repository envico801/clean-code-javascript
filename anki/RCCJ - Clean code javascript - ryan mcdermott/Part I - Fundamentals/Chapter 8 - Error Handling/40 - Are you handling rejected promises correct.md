========== Question ==========  

### Are you handling rejected Promises correctly?

Proper handling of Promise rejections is crucial for maintaining robust applications. Just like with try/catch blocks, ignoring Promise rejections can lead to silent failures, making debugging difficult and potentially leaving your application in an inconsistent state.

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

When handling Promise rejections, implement comprehensive error handling strategies that provide proper logging, user feedback, and error tracking. This creates more maintainable and reliable applications.

**Good:**

```javascript
getdata()
    .then((data) => {
        functionThatMightThrow(data);
    })
    .catch((error) => {
        // Detailed logging for debugging purposes
        console.error(error);

        // Provide user-friendly error messages
        notifyUserOfError(error);

        // Log to error tracking service for monitoring
        reportErrorToService(error);

        // Consider retrying the operation if appropriate
        // retry(operation, retryCount);
    });
```

========== Id ==========  
40

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 8 - Error Handling

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-8-Error-Handling::#40-Are-you-handling-rejected-promises-correct

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
