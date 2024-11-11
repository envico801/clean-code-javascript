========== Question ==========  

### Use consistent capitalization

JavaScript is untyped, so capitalization tells you a lot about your variables, functions, etc. These rules are subjective, so your team can choose whatever they want. The point is, no matter what you all choose, just be consistent.

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

FILE TAGS: #Javascript::#Coding-best-practices::#RCCJ-Clean-code-javascript-ryan-mcdermott::#Part-I-Fundamentals::#Chapter-9-Formatting::#41-Use-consistent-capitalization-javascript-i

Tags:

Reference:

Related:

```dataview
where file.name = this.file.name
```

QUESTION STATUS: Safe to store
