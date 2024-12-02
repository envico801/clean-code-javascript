========== Question ==========  

### Are you handling rejected Promises correctly?

Look at this Promise error handling. What's missing from this approach?

```javascript
getdata()
    .then((data) => {
        functionThatMightThrow(data);
    })
    .catch((error) => {
        console.log(error);
    });
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   Is just logging enough for production code?

-   What happens after the error is caught?

-   How would you handle temporary failures?

-   What information do users receive?

</details>  

========== Answer ==========  

**The Principle**:

Proper handling of Promise rejections is crucial for maintaining robust applications. Just like with try/catch blocks, ignoring Promise rejections can lead to silent failures, making debugging difficult and potentially leaving your application in an inconsistent state.

**Solution**:

Here's a more robust approach:

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

**Why is this better?**

This approach provides comprehensive error handling with proper logging, user feedback, and the possibility of recovery strategies like retrying operations.

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
