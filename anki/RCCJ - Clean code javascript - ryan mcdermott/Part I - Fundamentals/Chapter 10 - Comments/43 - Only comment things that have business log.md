========== Question ==========  

### Only comment things that have business logic complexity.

Comments are an apology, not a requirement. Good code _mostly_ documents itself.

**Bad:**

```javascript
function hashIt(data) {
    // The hash
    let hash = 0;
    // Length of string
    const length = data.length;
    // Loop through every character in data
    for (let i = 0; i < length; i++) {
        // Get character code.
        const char = data.charCodeAt(i);
        // Make the hash
        hash = (hash << 5) - hash + char;
        // Convert to 32-bit integer
        hash &= hash;
    }
}
```  

========== Answer ==========  

**Good:**

```javascript
function hashIt(data) {
    let hash = 0;
    const length = data.length;
    for (let i = 0; i < length; i++) {
        const char = data.charCodeAt(i);
        hash = (hash << 5) - hash + char;
        // Convert to 32-bit integer
        hash &= hash;
    }
}
```

========== Id ==========  
43

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#43-Only-comment-things-that-have-business-log

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
