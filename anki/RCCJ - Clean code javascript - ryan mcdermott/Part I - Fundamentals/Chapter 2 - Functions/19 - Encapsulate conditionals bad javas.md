========== Question ==========  

### Encapsulate conditionals

**Bad:**

```javascript
if (fsm.state === 'fetching' && isEmpty(listNode)) {
    // ...
}
```  

========== Answer ==========  

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#19-Encapsulate-conditionals-bad-javas

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
