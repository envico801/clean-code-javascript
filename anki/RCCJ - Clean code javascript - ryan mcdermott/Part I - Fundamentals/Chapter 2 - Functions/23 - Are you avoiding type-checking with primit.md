========== Question ==========  

### Are you avoiding type-checking with primitive types? (Part 2)

Type checking in JavaScript using primitive types often leads to overly complex and hard-to-maintain code. While type safety is important, manual type checking in JavaScript isn't the best approach. TypeScript provides a more robust solution by adding static typing capabilities.

Key benefits of using TypeScript over manual type checking:

-   Static type checking at compile time

-   Better IDE support and tooling

-   Cleaner, more readable code

-   Reduced runtime errors

**Bad:**

```javascript
function combine(val1, val2) {
    if (
        (typeof val1 === 'number' && typeof val2 === 'number') ||
        (typeof val1 === 'string' && typeof val2 === 'string')
    ) {
        return val1 + val2;
    }

    throw new Error('Must be of type String or Number');
}
```  

========== Answer ==========  

Instead of complex type checking logic, either use TypeScript for proper type safety or rely on JavaScript's dynamic nature with good testing practices. This makes the code more maintainable and easier to understand.

**Good:**

```javascript
function combine(val1, val2) {
    return val1 + val2;
}

// Or better, using TypeScript:
/*
function combine(val1: string | number, val2: string | number): string | number {
  return val1 + val2;
}
*/
```

========== Id ==========  
23

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#23-Are-you-avoiding-type-checking-with-primit

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
