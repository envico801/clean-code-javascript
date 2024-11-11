========== Question ==========  

### Favor functional programming over imperative programming

JavaScript isn't a functional language in the way that Haskell is, but it has a functional flavor to it. Functional languages can be cleaner and easier to test. Favor this style of programming when you can.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#18-Favor-functional-programming-over-imperati

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
