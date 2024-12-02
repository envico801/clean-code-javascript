========== Question ==========  

### Are you encapsulating conditionals for better readability?

What could make this conditional easier to understand?

```javascript
if (fsm.state === 'fetching' && isEmpty(listNode)) {
    // ...
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   What is this condition actually checking for?

-   How could we make the intent clearer?

-   Could we extract this logic into a well-named function?

-   How would this help with code reuse?

</details>  

========== Answer ==========  

**The Principle**:

Complex conditional statements can make code harder to read and understand. Extracting conditions into well-named functions improves code readability and reusability.

**Solution**:

Here's a clearer way to write it:

```javascript
function shouldShowSpinner(fsm, listNode) {
    return fsm.state === 'fetching' && isEmpty(listNode);
}

if (shouldShowSpinner(fsmInstance, listNodeInstance)) {
    // ...
}
```

**Why is this better?**

-   The condition's purpose is immediately clear

-   Logic can be reused elsewhere

-   Easier to test the condition independently

-   More self-documenting code

-   Easier to modify the condition if requirements change

========== Id ==========  
19

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#19-Are-you-encapsulating-conditionals-for-bet

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
