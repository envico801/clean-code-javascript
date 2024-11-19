========== Question ==========  

### Are you maintaining consistent capitalization in your code?

Consistent capitalization serves as a visual cue for the purpose and behavior of code elements in JavaScript. Since JavaScript is untyped, these naming conventions help developers quickly understand the role of different variables, functions, and classes. Following consistent patterns makes code more readable and maintainable.

**Bad:**

```javascript
const DAYS_IN_WEEK = 7;
const daysInMonth = 30;

const songs = ['Back In Black', 'Stairway to Heaven', 'Hey Jude'];
const Artists = ['ACDC', 'Led Zeppelin', 'The Beatles'];

function eraseDatabase() {}
function restore_database() {}

class animal {}
class Alpaca {}
```  

========== Answer ==========  

Following consistent capitalization rules makes code more predictable and easier to read. Here's a common convention:

-   Use UPPER_CASE for constants

-   Use PascalCase for class names

-   Use camelCase for functions and variables

-   Avoid mixing different naming conventions for similar elements

**Good:**

```javascript
const DAYS_IN_WEEK = 7;
const DAYS_IN_MONTH = 30;

const SONGS = ['Back In Black', 'Stairway to Heaven', 'Hey Jude'];
const ARTISTS = ['ACDC', 'Led Zeppelin', 'The Beatles'];

function eraseDatabase() {}
function restoreDatabase() {}

class Animal {}
class Alpaca {}
```

========== Id ==========  
41

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 9 - Formatting

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-9-Formatting::#41-Are-you-maintaining-consistent-capitalizat

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
