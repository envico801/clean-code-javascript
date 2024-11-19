========== Question ==========  

### Have you removed commented-out code from your codebase?

Commented-out code creates confusion and clutters the codebase. It raises questions about whether the code is still needed or why it was commented out. Modern version control systems like Git are the proper tools for maintaining code history.

**Bad:**

```javascript
doStuff();
// doOtherStuff();
// doSomeMoreStuff();
// doSoMuchStuff();
```  

========== Answer ==========  

Keep your codebase clean by removing commented-out code entirely. If you need to refer to old code, you can always find it in your version control history.

**Good:**

```javascript
doStuff();
```

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
