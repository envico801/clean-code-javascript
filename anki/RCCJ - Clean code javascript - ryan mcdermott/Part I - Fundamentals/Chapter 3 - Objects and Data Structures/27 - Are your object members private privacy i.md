========== Question ==========  

### Are your object members private?

Privacy in objects helps maintain encapsulation and prevents unauthorized access to internal state. While JavaScript didn't have built-in privacy features before ES2019, we can achieve privacy through closures.

Key benefits of private members:

-   Better encapsulation

-   Controlled access to internal state

-   Reduced risk of name collisions

-   Clearer interfaces

-   Easier refactoring

**Bad:**

```javascript
const Employee = function (name) {
    this.name = name;
};

Employee.prototype.getName = function getName() {
    return this.name;
};

const employee = new Employee('John Doe');
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name;
console.log(`Employee name: ${employee.getName()}`); // Employee name: undefined
```  

========== Answer ==========  

Using closures to create private members provides true privacy and prevents external modification of internal state.

**Good:**

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

========== Id ==========  
27

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 3 - Objects and Data Structures

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-3-Objects-and-Data-Structures::#27-Are-your-object-members-private-privacy-i

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
