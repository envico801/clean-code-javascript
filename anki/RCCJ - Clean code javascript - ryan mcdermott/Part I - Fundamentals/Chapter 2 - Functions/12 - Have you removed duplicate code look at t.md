========== Question ==========  

### Have you removed duplicate code?

Look at this code. What problems can you spot?

```javascript
function showDeveloperList(developers) {
    developers.forEach((developer) => {
        const expectedSalary = developer.calculateExpectedSalary();
        const experience = developer.getExperience();
        const githubLink = developer.getGithubLink();
        const data = {
            expectedSalary,
            experience,
            githubLink,
        };

        render(data);
    });
}

function showManagerList(managers) {
    managers.forEach((manager) => {
        const expectedSalary = manager.calculateExpectedSalary();
        const experience = manager.getExperience();
        const portfolio = manager.getMBAProjects();
        const data = {
            expectedSalary,
            experience,
            portfolio,
        };

        render(data);
    });
}
```

<details><summary>🔍 Hints</summary>

Think about:

-   What code is being repeated in both functions?

-   Could these functions be combined?

-   How could we handle the differences between developers and managers?

</details>  

========== Answer ==========  

**The Principle**:

Code duplication is one of the biggest enemies of maintainable software. When code is duplicated, changes need to be made in multiple places, increasing the chance of errors.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#remove-duplicate-code](https://github.com/ryanmcdermott/clean-code-javascript#remove-duplicate-code)

**Solution**:

Here's a better way to write it:

```javascript
function showEmployeeList(employees) {
    employees.forEach((employee) => {
        const expectedSalary = employee.calculateExpectedSalary();
        const experience = employee.getExperience();

        const data = {
            expectedSalary,
            experience,
        };

        switch (employee.type) {
            case 'manager':
                data.portfolio = employee.getMBAProjects();
                break;
            case 'developer':
                data.githubLink = employee.getGithubLink();
                break;
        }

        render(data);
    });
}
```

**Why is this better?**

-   Common code is now in one place

-   Employee-specific data is handled through a switch statement

-   Only one function to maintain and update

-   Easier to add new employee types in the future

========== Id ==========  
12

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#12-Have-you-removed-duplicate-code-look-at-t

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
