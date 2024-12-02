========== Question ==========  

### Are you maintaining consistent capitalization in your code?

Look at this code. What consistency issues do you spot?

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

<details><summary><b>🔍 Hints</b></summary>

<b>Think about</b>:

-   How are constants named?

-   What's the pattern for function names?

-   What's the convention for class names?

-   Are similar types of variables using the same capitalization?

</details>  

========== Answer ==========  

**The Principle**:

Consistent capitalization serves as a visual cue for the purpose and behavior of code elements in JavaScript. Since JavaScript is untyped, these naming conventions help developers quickly understand the role of different variables, functions, and classes. Following consistent patterns makes code more readable and maintainable.

**Solution**:

Here's the consistently formatted version:

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

**Why is this better?**

This code follows clear conventions:

-   UPPER_CASE for constants

-   PascalCase for class names

-   camelCase for functions and variables

-   Consistent naming patterns for similar elements

The consistent formatting makes the code more predictable and easier to read at a glance.

========== Id ==========  
41

---

DECK INFO

TARGET DECK: Javascript::Coding best practices::RCCJ - Clean code javascript - ryan mcdermott::Part I - Fundamentals::Chapter 7 - Concurrency

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-7-Concurrency::#41-Are-you-maintaining-consistent-capitalizat

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
