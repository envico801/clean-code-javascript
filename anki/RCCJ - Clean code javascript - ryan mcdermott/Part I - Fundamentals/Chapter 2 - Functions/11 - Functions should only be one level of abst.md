========== Question ==========  

### Functions should only be one level of abstraction

When you have more than one level of abstraction your function is usually doing too much. Splitting up functions leads to reusability and easier testing.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#11-Functions-should-only-be-one-level-of-abst

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
