========== Question ==========  

### Are you favoring functional programming over imperative programming?

Functional programming leads to more predictable code by avoiding state changes and side effects. It focuses on what should be computed rather than how it should be computed.

**Bad:**

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

========== Answer ==========  

Use functional methods like map, reduce, and filter to write more declarative code. This approach is more concise, easier to read, and less prone to errors.

**Good:**

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
