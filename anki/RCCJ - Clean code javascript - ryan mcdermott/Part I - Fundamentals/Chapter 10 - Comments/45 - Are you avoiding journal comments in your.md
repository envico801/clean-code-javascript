========== Question ==========  

### Are you avoiding journal comments in your code?

Journal comments that track changes are redundant when using version control systems. They become outdated quickly and add unnecessary noise to the codebase. Modern version control systems provide better tools for tracking changes and their authors.

**Bad:**

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

========== Answer ==========  

Instead of maintaining a manual change log in comments, use version control commands like `git log`, `git blame`, and meaningful commit messages to track changes.

**Good:**

```javascript
function combine(a, b) {
    return a + b;
}
```

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
