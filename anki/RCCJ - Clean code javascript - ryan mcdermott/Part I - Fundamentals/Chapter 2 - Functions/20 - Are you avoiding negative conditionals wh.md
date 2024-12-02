========== Question ==========  

### Are you avoiding negative conditionals?

What makes this conditional check harder to read and understand?

```javascript
function isDOMNodeNotPresent(node) {
    // ...
}

if (!isDOMNodeNotPresent(node)) {
    // ...
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   How many negatives are you processing mentally?

-   What is the actual intent of this code?

-   How could you make the condition more intuitive?

-   Would you need to think twice about what this code does?

</details>  

========== Answer ==========  

**The Principle**:

Negative conditionals are harder to understand at a glance because they require additional mental processing to understand what the code is not doing rather than what it is doing.

**Solution**:

Here's a clearer way to write it:

```javascript
function isDOMNodePresent(node) {
    // ...
}

if (isDOMNodePresent(node)) {
    // ...
}
```

**Why is this better?**

-   Immediately clear what we're checking for

-   No double negatives to process mentally

-   More natural to read and understand

-   Matches how we think about the condition

-   Easier to maintain and debug

========== Id ==========  
20

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#20-Are-you-avoiding-negative-conditionals-wh

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
