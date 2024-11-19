========== Question ==========  

### Have you removed duplicate code?

Code duplication is one of the biggest enemies of maintainable software. When code is duplicated, changes need to be made in multiple places, increasing the chance of errors and making maintenance more difficult.

**Reference**:

-   [https://github.com/ryanmcdermott/clean-code-javascript#remove-duplicate-code](https://github.com/ryanmcdermott/clean-code-javascript#remove-duplicate-code)

**Bad:**

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

========== Answer ==========  

Create abstractions that handle the common functionality while accommodating differences through polymorphism or conditional logic. This reduces code duplication and makes the codebase easier to maintain.

**Good:**

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

========== Id ==========  
12

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 2 - Functions

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-2-Functions::#12-Have-you-removed-duplicate-code-code-dupl

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
