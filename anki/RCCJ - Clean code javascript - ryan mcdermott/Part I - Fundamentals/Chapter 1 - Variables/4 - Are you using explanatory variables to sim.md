========== Question ==========  

### Are you using explanatory variables to simplify complex expressions?

Look at this code. What makes it hard to understand?

```javascript
const address = 'One Infinite Loop, Cupertino 95014';
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
saveCityZipCode(
    address.match(cityZipCodeRegex)[1],
    address.match(cityZipCodeRegex)[2],
);
```

<details><summary>🔍 Hints</summary>

Think about:

-   How many times is the regex match performed?

-   What do the array indices [1] and [2] represent?

-   How could we make this code more readable?

</details>  

========== Answer ==========  

**The Principle**:

Break down complex expressions into smaller, well-named parts to make the code's intent clear and avoid repeating operations.

**Solution**:

```javascript
const address = 'One Infinite Loop, Cupertino 95014';
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
saveCityZipCode(city, zipCode);
```

**Why is this better?**

We've used destructuring to give meaningful names to the regex matches and eliminated repeated operations. Each part of the code now clearly shows its purpose.

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
