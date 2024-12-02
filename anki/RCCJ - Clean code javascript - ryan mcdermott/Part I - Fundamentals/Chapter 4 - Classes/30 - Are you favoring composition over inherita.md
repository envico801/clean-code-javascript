========== Question ==========  

### Are you favoring composition over inheritance?

Look at this code. What's wrong with it?

```javascript
class Employee {
    constructor(name, email) {
        this.name = name;
        this.email = email;
    }

    // ...
}

// Bad because Employees "have" tax data, they aren't a type of tax data
class EmployeeTaxData extends Employee {
    constructor(ssn, salary) {
        super();
        this.ssn = ssn;
        this.salary = salary;
    }

    // ...
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   Is an EmployeeTaxData really a type of Employee?

-   What's the relationship between Employee and tax data?

-   Would this design be flexible if requirements change?

-   Is this a "has-a" or "is-a" relationship?

</details>  

========== Answer ==========  

**The Principle**:

Composition and inheritance are two fundamental approaches to code reuse in object-oriented programming. While inheritance is powerful, composition often provides more flexibility and looser coupling between components.

Key reasons to prefer composition:

-   Clear "has-a" relationships exist

-   More flexible design

-   Avoids deep inheritance hierarchies

-   Easier to change behavior at runtime

-   Better encapsulation

-   Reduces coupling between classes

When to use inheritance:

1. Clear "is-a" relationships exist

2. Base class behavior can be reused

3. You need to make global changes across all derived classes

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#prefer-composition-over-inheritance](https://github.com/ryanmcdermott/clean-code-javascript#prefer-composition-over-inheritance)

**Solution**:

```javascript
class EmployeeTaxData {
    constructor(ssn, salary) {
        this.ssn = ssn;
        this.salary = salary;
    }

    // ...
}

class Employee {
    constructor(name, email) {
        this.name = name;
        this.email = email;
    }

    setTaxData(ssn, salary) {
        this.taxData = new EmployeeTaxData(ssn, salary);
    }
    // ...
}
```

**Why is this better?**

-   Correctly models that an Employee has tax data

-   More flexible design

-   Easier to modify either class independently

-   Better encapsulation

-   Follows "has-a" relationship pattern

========== Id ==========  
30

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 4 - Classes

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-4-Classes::#30-Are-you-favoring-composition-over-inherita

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
