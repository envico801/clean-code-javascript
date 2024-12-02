========== Question ==========  

### Are your object members private?

Look at this code. What's wrong with it?

```javascript
const Employee = function (name) {
    this.name = name;
};

Employee.prototype.getName = function getName() {
    return this.name;
};

const employee = new Employee('John Doe');
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name; // Uh oh!
console.log(`Employee name: ${employee.getName()}`); // Employee name: undefined
```

<details><summary>🔍 Hints</summary>

Think about:

-   What happens if someone modifies the name directly?

-   How can we prevent accidental property deletion?

-   Is there a way to make the name truly private?

-   How can we control access to internal state?

</details>  

========== Answer ==========  

**The Principle**:

Privacy in objects helps maintain encapsulation and prevents unauthorized access to internal state. While JavaScript didn't have built-in privacy features before ES2019, we can achieve privacy through closures.

Key benefits of private members:

-   Better encapsulation

-   Controlled access to internal state

-   Reduced risk of name collisions

-   Clearer interfaces

-   Easier refactoring

**Solution**:

```javascript
function makeEmployee(name) {
    // 'name' is private due to closure
    return {
        getName() {
            return name;
        },
    };
}

const employee = makeEmployee('John Doe');
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name; // Has no effect
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
```

**Why is this better?**

-   Name property is truly private

-   Can't be modified or deleted from outside

-   Clear interface for accessing data

-   Better encapsulation

-   More robust and secure code

========== Id ==========  
27

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 3 - Objects and Data Structures

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-3-Objects-and-Data-Structures::#27-Are-your-object-members-private-look-at-t

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
