========== Question ==========  

### Are you avoiding side effects in your functions? (Part 1)

What's wrong with this code's approach to string manipulation?

```javascript
// Global variable referenced by following function.
// If we had another function that used this name, now it'd be an array and it could break it.
let name = 'Ryan McDermott';

function splitIntoFirstAndLastName() {
    name = name.split(' ');
}

splitIntoFirstAndLastName();

console.log(name); // ['Ryan', 'McDermott'];
```

<details><summary>🔍 Hints</summary>

Think about:

-   What happens to the original `name` variable?

-   Could this function cause problems in other parts of the code?

-   How would you test this function?

-   What if multiple functions need to use the original name?

</details>  

========== Answer ==========  

**The Principle**:

Side effects are changes that a function makes to any state outside its own scope. These can include modifying global variables, changing input parameters, or affecting the environment. They make code harder to test and can lead to unexpected bugs.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-1](https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-1)

**Solution**:

Here's a better way to write it:

```javascript
function splitIntoFirstAndLastName(name) {
    return name.split(' ');
}

const name = 'Ryan McDermott';
const newName = splitIntoFirstAndLastName(name);

console.log(name); // 'Ryan McDermott';
console.log(newName); // ['Ryan', 'McDermott'];
```

**Why is this better?**

-   Original data remains unchanged

-   Function is predictable and easier to test

-   Clear input/output relationship

-   Can use the original name value elsewhere in the code

-   Multiple functions can safely use the same input

========== Id ==========  
15

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#15-Are-you-avoiding-side-effects-in-your-func

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
