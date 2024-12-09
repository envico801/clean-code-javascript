========== Question ==========  

### Are your variable names easily searchable?

Look at this code. What's the problem here?

```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What does 86400000 represent?

-   How would you find all places using this number?

-   How could you make this value's purpose clearer?

</details>  

========== Answer ==========  

**The Principle**:

We will read more code than we will ever write. It's important that the code we do write is readable and searchable. By _not_ naming variables that end up being meaningful for understanding our program, we hurt our readers. Make your names searchable. Tools like [buddy.js](https://github.com/danielstjules/buddy.js) and [ESLint](https://github.com/eslint/eslint/blob/660e0918933e6e7fede26bc675a0763a6b357c94/docs/rules/no-magic-numbers.md) can help identify unnamed constants.

**Solution**:

```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```

**Why is this better?**

The constant name clearly explains what the number represents, making the code self-documenting and easier to search for and update.

========== Id ==========  
3

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 1 - Variables

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-1-Variables::#3-Are-your-variable-names-easily-searchable

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
