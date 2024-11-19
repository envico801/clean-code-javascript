========== Question ==========  

### Are you avoiding mental mapping in your code?

Don't force readers to translate between different contexts. Using single-letter variables or abbreviated names requires the reader to mentally map these to their actual meaning.

**Bad:**

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

========== Answer ==========  

Use complete, descriptive variable names that don't require the reader to remember what abbreviations stand for. This makes code immediately understandable without having to scroll up to check variable meanings.

**Good:**

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
