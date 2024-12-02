========== Question ==========  

### Are you properly handling caught errors?

Look at this error handling code. What's problematic about this approach?

```javascript
try {
    functionThatMightThrow();
} catch (error) {
    console.log(error);
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What happens to this error after it's logged?

-   How would you debug issues in production?

-   How would users know something went wrong?

-   What information are you capturing about the error?

</details>  

========== Answer ==========  

**The Principle**:

Proper error handling is crucial for maintaining robust applications. Simply catching errors without handling them appropriately can lead to silent failures and make debugging extremely difficult.

**Solution**:

Here's a better approach:

```javascript
try {
    functionThatMightThrow();
} catch (error) {
    // Detailed error logging for debugging
    console.error(error);

    // Inform the user in a user-friendly way
    notifyUserOfError(error);

    // Track errors in your monitoring system
    reportErrorToService(error);
    // OR do all three!
}
```

**Why is this better?**

This approach ensures errors are properly logged, users are informed, and the development team can track and monitor issues effectively.

========== Id ==========  
39

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 8 - Error Handling

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-8-Error-Handling::#39-Are-you-properly-handling-caught-errors-l

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
