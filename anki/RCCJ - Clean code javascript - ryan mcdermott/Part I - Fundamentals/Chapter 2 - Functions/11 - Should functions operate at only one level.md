========== Question ==========  

### Should functions operate at only one level of abstraction?

Each function should work at a single level of abstraction. This means all operations within the function should be at a similar conceptual level, making the code easier to understand and maintain.

**Bad:**

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

========== Answer ==========  

Break down complex functions into smaller, focused functions where each function handles one level of abstraction. This makes the code more readable and maintainable by separating concerns.

**Good:**

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
