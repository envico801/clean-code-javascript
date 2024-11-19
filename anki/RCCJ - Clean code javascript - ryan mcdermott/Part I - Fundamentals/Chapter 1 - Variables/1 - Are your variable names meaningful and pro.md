========== Question ==========  

### Are your variable names meaningful and pronounceable?

When naming variables, use clear, descriptive names that explain their purpose. Avoid abbreviations and cryptic shorthand that might confuse other developers.

**Bad:**

```javascript
const yyyymmdstr = moment().format('YYYY/MM/DD');
```  

========== Answer ==========  

The variable name should clearly indicate that we're working with a date. Using `currentDate` immediately tells other developers the purpose of this variable.

**Good:**

```javascript
const currentDate = moment().format('YYYY/MM/DD');
```

========== Id ==========  
1

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#1-Are-your-variable-names-meaningful-and-pro

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
