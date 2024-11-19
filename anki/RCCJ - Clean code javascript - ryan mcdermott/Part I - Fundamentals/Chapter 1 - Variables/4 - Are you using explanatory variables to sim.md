========== Question ==========  

### Are you using explanatory variables to simplify complex expressions?

Break down complex expressions into smaller, well-named parts. This makes the code easier to understand and maintain by making each step's purpose clear.

**Bad:**

```javascript
const address = 'One Infinite Loop, Cupertino 95014';
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
saveCityZipCode(
    address.match(cityZipCodeRegex)[1],
    address.match(cityZipCodeRegex)[2],
);
```  

========== Answer ==========  

Using destructuring and intermediate variables makes complex operations more readable. Each step becomes self-documenting through clear variable names.

**Good:**

```javascript
const address = 'One Infinite Loop, Cupertino 95014';
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
saveCityZipCode(city, zipCode);
```

========== Id ==========  
4

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#4-Are-you-using-explanatory-variables-to-sim

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
