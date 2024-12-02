========== Question ==========  

### Should functions operate at only one level of abstraction?

What makes this code difficult to understand and maintain?

```javascript
function parseBetterJSAlternative(code) {
    const REGEXES = [
        // ...
    ];

    const statements = code.split(' ');
    const tokens = [];
    REGEXES.forEach((REGEX) => {
        statements.forEach((statement) => {
            // ...
        });
    });

    const ast = [];
    tokens.forEach((token) => {
        // lex...
    });

    ast.forEach((node) => {
        // parse...
    });
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   How many different operations are happening here?

-   Are all these operations at the same conceptual level?

-   How could we organize this to make the process clearer?

</details>  

========== Answer ==========  

**The Principle**:

Each function should work at a single level of abstraction. This means all operations within the function should be at a similar conceptual level, making the code easier to understand and maintain.

**Solution**:

```javascript
function parseBetterJSAlternative(code) {
    const tokens = tokenize(code);
    const syntaxTree = parse(tokens);
    syntaxTree.forEach((node) => {
        // parse...
    });
}

function tokenize(code) {
    const REGEXES = [
        // ...
    ];

    const statements = code.split(' ');
    const tokens = [];
    REGEXES.forEach((REGEX) => {
        statements.forEach((statement) => {
            tokens.push(/* ... */);
        });
    });

    return tokens;
}

function parse(tokens) {
    const syntaxTree = [];
    tokens.forEach((token) => {
        syntaxTree.push(/* ... */);
    });

    return syntaxTree;
}
```

**Why is this better?**

-   The main function now operates at a single, high level of abstraction

-   Each operation has been broken into its own function with a clear purpose

-   The code tells a story: tokenize → parse → return

-   Each function handles one specific task at one specific level of detail

========== Id ==========  
11

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#11-Should-functions-operate-at-only-one-level

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
