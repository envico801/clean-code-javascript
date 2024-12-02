========== Question ==========  

### Have you removed commented-out code from your codebase?

Look at this code snippet. What problems might it cause in a real project?

```javascript
doStuff();
// doOtherStuff();
// doSomeMoreStuff();
// doSoMuchStuff();
```

<details><summary>🔍 Hints</summary>

Think about:

-   Why might these lines be commented out?

-   How does this affect code readability?

-   What questions might other developers have when they see this?

-   What's a better way to handle old/unused code?

</details>  

========== Answer ==========  

**The Principle:**

Commented-out code creates confusion and clutters the codebase. It raises questions about whether the code is still needed or why it was commented out. Modern version control systems like Git are the proper tools for maintaining code history.

**Solution**:

Here's how the code should look:

```javascript
doStuff();
```

**Why is this better?**

-   Clean and clear - no ambiguity about what code is actually being used

-   No mental overhead wondering if the commented code is important

-   If you need the old code, you can find it in your version control history

-   Easier to maintain and review code without the clutter

========== Id ==========  
44

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#44-Have-you-removed-commented-out-code-from-y

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
