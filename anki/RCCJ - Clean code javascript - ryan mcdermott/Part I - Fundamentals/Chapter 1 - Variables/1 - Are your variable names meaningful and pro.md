========== Question ==========  

### Are your variable names meaningful and pronounceable?

Look at this code. What's wrong with it?

```javascript
const yyyymmdstr = moment().format('YYYY/MM/DD');
```

<details><summary>🔍 Hints</summary>

Think about:

-   What does this variable store?

-   Would other developers understand it easily?

-   How would you improve it?

</details>  

========== Answer ==========  

**The Principle**:

When naming variables, use clear, descriptive names that explain their purpose. Avoid abbreviations and cryptic shorthand that might confuse other developers.

**Solution**:

Here's a better way to write it:

```javascript
const currentDate = moment().format('YYYY/MM/DD');
```

**Why is this better?**

The variable name clearly indicates that we're working with a date. Using `currentDate` immediately tells other developers the purpose of this variable.

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
