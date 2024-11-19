========== Question ==========  

### Are you using the same vocabulary for the same type of variable?

When referring to the same type of data or operation, maintain consistency in your naming conventions throughout your codebase. This reduces cognitive load and makes the code more predictable.

**Bad:**

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```  

========== Answer ==========  

Choose one term and stick with it. If you decide to use `user`, use it consistently throughout your application instead of mixing terms like `client` or `customer` for the same concept.

**Good:**

```javascript
getUser();
```

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
