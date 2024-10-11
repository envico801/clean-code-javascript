========== Question ==========  

### Don't ignore caught errors

Doing nothing with a caught error doesn't give you the ability to ever fix

or react to said error. Logging the error to the console (`console.log`)

isn't much better as often times it can get lost in a sea of things printed

to the console. If you wrap any bit of code in a `try/catch` it means you

think an error may occur there and therefore you should have a plan,

or create a code path, for when it occurs.

**Bad:**

```javascript
try {
    functionThatMightThrow();
} catch (error) {
    console.log(error);
}
```  

========== Answer ==========  

**Good:**

```javascript
try {
    functionThatMightThrow();
} catch (error) {
    // One option (more noisy than console.log):
    console.error(error);
    // Another option:
    notifyUserOfError(error);
    // Another option:
    reportErrorToService(error);
    // OR do all three!
}
```

========== Id ==========  
39

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 8 - Error Handling

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-8-Error-Handling::#39-Don-t-ignore-caught-errors-doing-nothing-w

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
