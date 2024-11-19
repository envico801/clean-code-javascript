========== Question ==========  

### Are you avoiding positional markers in your code?

Positional markers or section dividers add visual noise without providing real value. Well-structured code with meaningful names and proper organization should make the code's structure clear without needing these artificial divisions.

**Bad:**

```javascript
////////////////////////////////////////////////////////////////////////////////
// Scope Model Instantiation
////////////////////////////////////////////////////////////////////////////////
$scope.model = {
    menu: 'foo',
    nav: 'bar',
};

////////////////////////////////////////////////////////////////////////////////
// Action setup
////////////////////////////////////////////////////////////////////////////////
const actions = function () {
    // ...
};
```  

========== Answer ==========  

Instead of using visual markers, organize your code into well-named functions and modules. Use proper spacing and meaningful names to create natural visual structure.

**Good:**

```javascript
$scope.model = {
    menu: 'foo',
    nav: 'bar',
};

const actions = function () {
    // ...
};
```

Best practices for comments:

1. Use comments to explain complex business logic or algorithms

2. Write comments that explain "why" rather than "what"

3. Keep comments up-to-date with code changes

4. Use version control for tracking changes instead of comment-based histories

5. Let well-structured code speak for itself through clear naming and organization

========== Id ==========  
46

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#46-Are-you-avoiding-positional-markers-in-you

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
