========== Question ==========  

### Are you avoiding journal comments in your code?

Look at this function. What's problematic about its documentation?

```javascript
/**
 * 2016-12-20: Removed monads, didn't understand them (RM)
 * 2016-10-01: Improved using special monads (JP)
 * 2016-02-03: Removed type-checking (LI)
 * 2015-03-14: Added combine with type-checking (JR)
 */
function combine(a, b) {
    return a + b;
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   How useful is this history in the code itself?

-   What happens when the code changes again?

-   What tools could better track this information?

-   How does this affect code readability?

</details>  

========== Answer ==========  

**The Principle:**

Journal comments that track changes are redundant when using version control systems. They become outdated quickly and add unnecessary noise to the codebase. Modern version control systems provide better tools for tracking changes and their authors.

**Solution**:

Here's how the code should look:

```javascript
function combine(a, b) {
    return a + b;
}
```

**Why is this better?**

-   Clean code without historical clutter

-   History is properly maintained in version control (git)

-   Changes can be tracked with `git log` or `git blame`

-   Documentation stays focused on current code behavior

-   Easier to maintain and update

========== Id ==========  
45

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#45-Are-you-avoiding-journal-comments-in-your

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
