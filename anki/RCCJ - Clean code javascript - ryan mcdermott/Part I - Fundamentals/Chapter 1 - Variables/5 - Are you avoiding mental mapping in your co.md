========== Question ==========  

### Are you avoiding mental mapping in your code?

What's problematic about this code?

```javascript
const locations = ['Austin', 'New York', 'San Francisco'];
locations.forEach((l) => {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `l` for again?
    dispatch(l);
});
```

<details><summary>🔍 Hints</summary>

Think about:

-   What does 'l' represent?

-   How much mental effort is needed to keep track of what 'l' means?

-   What happens if you come back to this code after a few weeks?

</details>  

========== Answer ==========  

**The Principle**:

Don't force readers to translate between different contexts. Using single-letter variables or abbreviated names requires the reader to mentally map these to their actual meaning.

**Solution**:

```javascript
const locations = ['Austin', 'New York', 'San Francisco'];
locations.forEach((location) => {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    dispatch(location);
});
```

**Why is this better?**

Using the full word `location` instead of `l` makes the code immediately understandable without requiring any mental translation.

========== Id ==========  
5

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#5-Are-you-avoiding-mental-mapping-in-your-co

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
