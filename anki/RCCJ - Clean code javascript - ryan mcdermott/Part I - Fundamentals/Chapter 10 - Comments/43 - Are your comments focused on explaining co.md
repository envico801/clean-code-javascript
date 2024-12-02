========== Question ==========  

### Are your comments focused on explaining complex business logic?

Look at this code. What's wrong with these comments?

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

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What value do these comments add?

-   Are they explaining anything that isn't obvious from the code?

-   What would be more useful to explain here?

-   When should we actually use comments?

</details>  

========== Answer ==========  

**The Principle**:

Comments should explain the "why" behind complex business logic, not the "what" or "how" that should be evident from well-written code. Excessive comments often indicate that the code itself could be clearer or better structured.

**Solution**:

Here's better use of comments:

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

**Why is this better?**

-   Removed comments that merely repeat what the code says

-   Kept only the comment that explains the reasoning behind the 32-bit conversion

-   The code is now cleaner and easier to read

-   The remaining comment adds actual value by explaining the "why"

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
