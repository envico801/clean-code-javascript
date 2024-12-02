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

<details><summary>🔍 Hints</summary>

Think about:

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

### Chapter 9 - Formatting

Formatting is subjective. Like many rules herein, there is no hard and fast rule that you must follow. The main point is DO NOT ARGUE over formatting. There are [tons of tools](https://standardjs.com/rules.html) to automate this. Use one! It's a waste of time and money for engineers to argue over formatting.

For things that don't fall under the purview of automatic formatting (indentation, tabs vs. spaces, double vs. single quotes, etc.) look here for some guidance.

========== Id ==========  
40

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 7 - Concurrency

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#40-Are-you-handling-rejected-promises-correct

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
