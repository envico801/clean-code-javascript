========== Question ==========  

### Are you encapsulating conditionals for better readability?

Complex conditional statements can make code harder to read and understand. Extracting conditions into well-named functions improves code readability and reusability.

**Bad:**

```javascript
if (fsm.state === 'fetching' && isEmpty(listNode)) {
    // ...
}
```  

========== Answer ==========  

Create functions with descriptive names that encapsulate the conditional logic. This makes the code self-documenting and easier to maintain.

**Good:**

```javascript
function shouldShowSpinner(fsm, listNode) {
    return fsm.state === 'fetching' && isEmpty(listNode);
}

if (shouldShowSpinner(fsmInstance, listNodeInstance)) {
    // ...
}
```

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
