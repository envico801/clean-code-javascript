========== Question ==========  

### Are you avoiding positional markers in your code?

Look at this code. What's wrong with how it's organized?

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

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   What purpose do these dividers serve?

-   Do they make the code more maintainable?

-   How else could we make code structure clear?

-   What happens when you need to add new sections?

</details>  

========== Answer ==========  

**The Principle**:

Positional markers or section dividers add visual noise without providing real value. Well-structured code with meaningful names and proper organization should make the code's structure clear without needing these artificial divisions.

**Solution**:

Here's how to better structure the code:

```javascript
// Consider splitting into separate files if these are distinct concerns
$scope.model = {
    menu: 'foo',
    nav: 'bar',
};

const actions = function () {
    // ...
};
```

**Why is this better?**

-   No visual noise from ASCII dividers

-   Better naming makes the purpose of each section clear

-   Code organization is achieved through proper structure, not visual markers

-   Suggests better architectural decisions (like separating concerns into modules)

-   Easier to maintain and modify without needing to update dividers

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
