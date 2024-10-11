========== Question ==========  

### Avoid positional markers

They usually just add noise. Let the functions and variable names along with the

proper indentation and formatting give the visual structure to your code.

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

========== Id ==========  
46

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 10 - Comments

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-10-Comments::#46-Avoid-positional-markers-they-usually-just

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```
QUESTION STATUS: Safe to store
