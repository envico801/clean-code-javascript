========== Question ==========  

### Are you favoring functional programming over imperative programming?

Look at this code for calculating total lines of code. What could be improved?

```javascript
const programmerOutput = [
    {
        name: 'Uncle Bobby',
        linesOfCode: 500,
    },
    {
        name: 'Suzie Q',
        linesOfCode: 1500,
    },
    {
        name: 'Jimmy Gosling',
        linesOfCode: 150,
    },
    {
        name: 'Gracie Hopper',
        linesOfCode: 1000,
    },
];

let totalOutput = 0;

for (let i = 0; i < programmerOutput.length; i++) {
    totalOutput += programmerOutput[i].linesOfCode;
}
```

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What state is being maintained in this code?

-   How could we make this more declarative?

-   What array methods could simplify this?

-   How could we make this more readable?

</details>  

========== Answer ==========  

**The Principle**:

Functional programming leads to more predictable code by avoiding state changes and side effects. It focuses on what should be computed rather than how it should be computed.

**Solution**:

Here's a more functional approach:

```javascript
const programmerOutput = [
    {
        name: 'Uncle Bobby',
        linesOfCode: 500,
    },
    {
        name: 'Suzie Q',
        linesOfCode: 1500,
    },
    {
        name: 'Jimmy Gosling',
        linesOfCode: 150,
    },
    {
        name: 'Gracie Hopper',
        linesOfCode: 1000,
    },
];

const totalOutput = programmerOutput.reduce(
    (totalLines, output) => totalLines + output.linesOfCode,
    0,
);
```

**Why is this better?**

-   No mutable variables

-   More declarative - shows what we want to achieve

-   Shorter and more expressive

-   Easier to chain with other operations if needed

-   Less prone to off-by-one errors

========== Id ==========  
18

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#18-Are-you-favoring-functional-programming-ov

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
