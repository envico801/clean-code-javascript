========== Question ==========  

### Are you avoiding type-checking in your code? (Part 2)

Look at this code. What's wrong with it?

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

<details><summary>🔍 Hints</summary>

Think about:

-   How readable is this type-checking code?

-   What happens if we need to support more types?

-   Is there a better way to ensure type safety?

-   How might TypeScript help here?

</details>  

========== Answer ==========  

**The Principle**:

Manual type checking in JavaScript often leads to complex, hard-to-maintain code. Instead, either embrace JavaScript's dynamic nature with good testing practices or use TypeScript for proper type safety.

Key benefits of using TypeScript over manual type checking:

-   Static type checking at compile time

-   Better IDE support and tooling

-   Cleaner, more readable code

-   Reduced runtime errors

**Solution**:

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

**Why is this better?**

-   Cleaner, more readable code

-   No complex type-checking logic

-   With TypeScript, you get:

    -   Compile-time type checking

    -   Better IDE support

    -   Clearer function signatures

-   More maintainable and scalable

========== Id ==========  
23

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#23-Are-you-avoiding-type-checking-in-your-cod

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
