========== Question ==========  

### Are your comments focused on explaining complex business logic?

Comments should explain the "why" behind complex business logic, not the "what" or "how" that should be evident from well-written code. Excessive comments often indicate that the code itself could be clearer or better structured.

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

The improved version removes redundant comments that simply describe what the code is doing. Only keep comments that explain complex algorithms or business decisions that aren't immediately obvious from the code.

**Good:**

```javascript
function hashIt(data) {
    let hash = 0;
    const length = data.length;
    for (let i = 0; i < length; i++) {
        const char = data.charCodeAt(i);
        hash = (hash << 5) - hash + char;
        // Converting to 32-bit integer is necessary to handle large strings
        // and maintain consistent hash values across different platforms
        hash &= hash;
    }
}
```

========== Id ==========  
43

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#43-Are-your-comments-focused-on-explaining-co

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
