========== Question ==========  

### Make objects have private members

This can be accomplished through closures (for ES5 and below).

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

**Good:**

```javascript
function makeEmployee(name) {
    return {
        getName() {
            return name;
        },
    };
}
const employee = makeEmployee('John Doe');
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name;
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
```

========== Id ==========  
27

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 3 - Objects and Data Structures

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-3-Objects-and-Data-Structures::#27-Make-objects-have-private-members-this-can

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
