========== Question ==========  

### Are you using the same vocabulary for the same type of variable?

Look at this code. What's wrong with it?

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What concept do all these functions deal with?

-   Is the naming consistent?

-   How could this create confusion for other developers?

</details>  

========== Answer ==========  

**The Principle**:

When referring to the same type of data or operation, maintain consistency in your naming conventions throughout your codebase. This reduces cognitive load and makes the code more predictable.

**Solution**:

```javascript
getUser();
```

**Why is this better?**

We've chosen one term (`user`) and used it consistently. This avoids confusion about whether a `client`, `customer`, or `user` might be handled differently.

========== Id ==========  
2

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#2-Are-you-using-the-same-vocabulary-for-the

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
