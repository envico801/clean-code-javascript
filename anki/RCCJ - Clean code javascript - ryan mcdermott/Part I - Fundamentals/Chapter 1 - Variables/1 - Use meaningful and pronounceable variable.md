========== Question ==========  

### Use meaningful and pronounceable variable names

**Bad:**

```javascript
const yyyymmdstr = moment().format('YYYY/MM/DD');
```  

========== Answer ==========  

**Good:**

```javascript
const currentDate = moment().format('YYYY/MM/DD');
```

========== Id ==========  
1

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#1-Use-meaningful-and-pronounceable-variable

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
